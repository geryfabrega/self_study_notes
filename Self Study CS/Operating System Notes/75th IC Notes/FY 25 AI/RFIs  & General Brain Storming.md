
RFI: How are the video files stored for our Customer? S3 bucket? Shared drive? Azure Storage Accounts? 
How can we ingest? One time lift? ingestion service? BYOD?
Asynchronous Ingestion service with workers may be the ideal candidate with Meta Data Store *We ship our own postgres and or Misvis*


We may just need to onoboard our meta data service + pipeline in their infra. 

Lets use apache Air flow to incorpoarete dat processing into DAG.
We can chuck videos and run in parallell, 

Break videos into chunks and then just run N chucks per airflow DAG.

| Task                          | Recommendation                                              |
| ----------------------------- | ----------------------------------------------------------- |
| Store intermediate data?      | Yes, in S3 or shared blob storage                           |
| Run DAG per chunk?            | Yes, or use dynamic mapping                                 |
| Chunk large videos?           | Yes, into N parts                                           |
| Store original video for RAG? | Optional — chunk-level transcript/embeddings usually enough |
| Track jobs?                   | Yes, use Postgres or a queue                                |
| Trigger DAGs in parallel?     | Yes — Airflow supports it natively                          |
|                               |                                                             |


Have a polling script check S3 and chunk everything in small portions, have this run every few minutes. after creating smaller chunks in a different S3 folder, write to to table saying chunk is ready. include the chunk video origin. have a state saying its ready.


Also have a master python run every minutes to look for new jobs in the table. it will pick up groups of 10 videos segments and then file away to the Apache Airflow API. Then the API will process each segment and dump the outputs into a vector database, then state the metadata table as complete. 
