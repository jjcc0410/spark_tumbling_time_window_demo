## Time Window demo

### Explanation

The TradeSummary class processes real-time trade data using PySpark's Structured Streaming. It reads raw trade data from a Kafka stream table (kafka_bz), transforms it using a defined schema, and calculates total Buy and Sell amounts using stateful tumbling window aggregation.

Tumbling windows are fixed, non-overlapping 15-minute intervals where trades are grouped by their CreatedTime. Late data is managed with a 30-minute watermark to ensure timely aggregation while accounting for delayed events. The results, including the start and end times of each window and aggregated trade amounts, are saved to a silver table (trade_summary) with fault tolerance enabled via checkpointing.

### Visualization

![imagen](https://github.com/user-attachments/assets/f4701f49-d5e3-45c4-af9c-76838323ec83)
