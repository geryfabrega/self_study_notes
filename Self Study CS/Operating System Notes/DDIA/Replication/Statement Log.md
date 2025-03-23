A log that states an action that occured (INSERT, UPDATE, DELETE) Statement
This is forwarded to the followers of the leader. Each followers reads the logs and applies them as if they are the leader them selves

Applying logs is good however any non determinittic statements like "Random" or "time now" will yield different results

Leader can replace non determintisc function with a hardcoded value for the followers to apply.

