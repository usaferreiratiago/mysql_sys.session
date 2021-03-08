# mysql_sys.session

SELECT 
    `sys`.`processlist`.`thd_id` AS `thd_id`,
    `sys`.`processlist`.`conn_id` AS `conn_id`,
    `sys`.`processlist`.`user` AS `user`,
    `sys`.`processlist`.`db` AS `db`,
    `sys`.`processlist`.`command` AS `command`,
    `sys`.`processlist`.`state` AS `state`,
    `sys`.`processlist`.`time` AS `time`,
    `sys`.`processlist`.`current_statement` AS `current_statement`,
    `sys`.`processlist`.`statement_latency` AS `statement_latency`,
    `sys`.`processlist`.`progress` AS `progress`,
    `sys`.`processlist`.`lock_latency` AS `lock_latency`,
    `sys`.`processlist`.`rows_examined` AS `rows_examined`,
    `sys`.`processlist`.`rows_sent` AS `rows_sent`,
    `sys`.`processlist`.`rows_affected` AS `rows_affected`,
    `sys`.`processlist`.`tmp_tables` AS `tmp_tables`,
    `sys`.`processlist`.`tmp_disk_tables` AS `tmp_disk_tables`,
    `sys`.`processlist`.`full_scan` AS `full_scan`,
    `sys`.`processlist`.`last_statement` AS `last_statement`,
    `sys`.`processlist`.`last_statement_latency` AS `last_statement_latency`,
    `sys`.`processlist`.`current_memory` AS `current_memory`,
    `sys`.`processlist`.`last_wait` AS `last_wait`,
    `sys`.`processlist`.`last_wait_latency` AS `last_wait_latency`,
    `sys`.`processlist`.`source` AS `source`,
    `sys`.`processlist`.`trx_latency` AS `trx_latency`,
    `sys`.`processlist`.`trx_state` AS `trx_state`,
    `sys`.`processlist`.`trx_autocommit` AS `trx_autocommit`,
    `sys`.`processlist`.`pid` AS `pid`,
    `sys`.`processlist`.`program_name` AS `program_name`
FROM
    `sys`.`processlist`
WHERE
    ((`sys`.`processlist`.`conn_id` IS NOT NULL)
        AND (`sys`.`processlist`.`command` <> 'Daemon'))
