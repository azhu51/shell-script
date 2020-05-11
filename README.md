# shell-script
collect some practical shell script

<p></p>

查询是否有重复行
```bash
cat FILENAME | awk 'a[$1]++'
```
读取HDFS最大分区路径
```bash
hdfs dfs -ls HDFS_FILE | awk '$6 <= "DATE"' | awk '$5 > FILE_SIZE' | awk -F" " '{print $6$7" "$5" "$8}' | sort -nr | sed -n '1p' | awk '{print $3}'
```

