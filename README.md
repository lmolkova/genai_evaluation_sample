# Evaluation events sample

Prerequisites:

- Docker

How to run:

1. Set `OPENAT_API_KEY` and `APPLICATIONINSIGHTS_CONNECTION_STRING`
2. run with `docker-compose up`
3. open http://localhost:8085
4. add prompt and submit
5. provide feedback
6. You can check generated telemetry in Application Insights resource or locally via Aspire dashboard (http://localhost:18888) included in docker-compose

API access:

1. Set `OPENAT_API_KEY` and `APPLICATIONINSIGHTS_CONNECTION_STRING`,
2. run with `docker-compose up`
3. `curl http://localhost:8000/chat?prompt=tell%20me%20a%20joke` to get completion and metadata. It'd return something like

   ```json
    {
      "completion": "Why did the scarecrow win an award? \n\nBecause he was outstanding in his field! \n\nAnd you know, he really knew how to raise the stakes – just ask the corn! 🌽😄",
      "metadata": {
        "response_id": "chatcmpl-A1jhMgJEH87R40j5xrhIiZIwc1VFY",
        "trace_id": 3.0855353271240902e+38,
        "span_id": 2824187595407880700
      }
    }
   ```

4. `curl http://localhost:8000/feedback?feedback=-1&trace_id=308553532712409009926940644798237390457&span_id=2824187595407880639&response_id=chatcmpl-A1jhMgJEH87R40j5xrhIiZIwc1VFY` to send feedback.
