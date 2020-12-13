# Queing

This feature package contains monitoring of my position in the queue at the Megekko.nl webshop for receiving the AMD processor I bought.

Currently this package is disabled, since I received the processor. Maybe I can reuse this later for a graphics card queue when I order one of those :)

## Data flow:

1. The REST sensor sensor.queue_processor checks the megekko.nl website each hour
    - it saves the raw result in the status and data attributes
    - if it can find "123 van de 456" string in the data, it saves that part to the state
      (otherwise the state will become 'unavailable'
2. The 'remember_text.yaml' automation monitors the state from #1, and if not unavailable:
    - copies it to the input_text.queue_processor entity
      (which is persistent across restarts, while the REST sensor is not)
    - notifies my phone
3. The template sensor sensor.queue_processor_position extracts the first number
   - indicates my position in the queue
   - so (this-1) people get their processor before me
4. The template sensor sensor.queue_processor_total_waiting extracts the second number
   - indicates the total number of people in the queue
5. The values from #3 and #4 are used in the UI