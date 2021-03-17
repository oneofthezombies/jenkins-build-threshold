# jenkins-build-threshold
```python
# pip install python-jenkins
import jenkins

server = jenkins.Jenkins('http://localhost:8080', username='hunhoekim', password='hunhoekim')
job = server.get_job_info('test-script-inline')
last_build_number = job['lastCompletedBuild']['number']
last_success_number = job['lastSuccessfulBuild']['number']

failed_build_count = last_build_number - last_success_number
angry_threshold = 2
if failed_build_count >= angry_threshold:
    print("i will kill you.")
```