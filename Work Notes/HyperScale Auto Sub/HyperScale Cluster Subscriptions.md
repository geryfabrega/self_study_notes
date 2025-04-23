
In CMS run this query

```
select subscription_purpose, subscription_id, current_arm_storage_accounts,max_arm_storage_accounts, create_time from cluster_subscriptions where subscription_purpose = 'HsPageServerRaGrs'
```

