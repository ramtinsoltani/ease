- `ease.task(name, callback)`: Defines a task with the given name and calls the callback for performing the task. The call back should either return void (for synchronous execution) or return a void promise (for asynchronous execution). Callback will be called with two parameters: `jobName` which holds the current executing job name and either `suspend`, which is a function that suspends the current task from running (only available on the `:before` hook) or `error` which is an error object (only available on the `:error` hook.) Return the ease instance for chaining.
- `ease.job(name, tasks [,options])`: Defines a job with the given name and a list of the tasks to execute in order. An optional [Job Execution Options](#usage-job-execution-options) object can be provided. Return the ease instance for chaining.
- `ease.hook(name, callback)`: Defines a job hook with a callback. Return the ease instance for chaining.
- `ease.suspend(jobName)`: Suspends a job by name.
- `ease.info(jobName)`: Returns an object with members `tasks` and `options` which are a list of the registered tasks and the options of the job. This info can help dynamically redefining jobs.
- `ease.log(message)`: Logs a message which will be shown on the console and logged into `ease.log` file.
- `ease.install(taskName, plugin, ...args)`: Installs a plugin as a task with the given name. `...args` will be sent to the plugin. Return the ease instance for chaining.