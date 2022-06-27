# Run workflows

You can run any of the workflows defined in `.dstack/workflows.yaml` using the CLI.

Here's an example: 

```bash
dstack run download 
```

!!! info "Git"
    Be sure to invoke the dstack CLI from the repository directory.

    As long as your project is under Git, you don't have to commit local changes before running workflows.
    dstack tracks staged local changes automatically and allows you to see them in the user interface
    for every run.

Once you've run a workflow, you'll see it in the user interface.
To see recent runs from the CLI, use the following command:

```bash
dstack runs
```

[//]: # (TODO: Show a screennshot of repo diff)

### Variables

If you defined workflow variables within the `.dstack/variables.yaml` file, you can override any of them via the 
arguments of the `dstack run` command: 

```bash
dstack run train --epoch 100 --seed 2
```

[//]: # (TODO: Tell how to override any workflow parameters)

[//]: # (TODO: Tell about statuses)

[//]: # (TODO: Tell about availability issues)

### Logs

The output of running workflows is tracked in real-time and can be accessed through the user interface
or the CLI.

To access the output through the CLI, use the following command:

```bash
dstack logs <run-name>
```

If you'd like to see the output in real-time through the CLI, add the `-f` (or `--follow`) argument:

```bash
dstack logs <run-name> -f
```

!!! info "Experiment metrics"
    Be sure not to use logs to track experiment metrics. Instead, it's recommended
    that you use specialized APIs such as TensorBoard, WandB, Comet, or Neptune.

[//]: # (TODO: Add a link to more information on experiment tracking)

### Artifacts

By default, the output artifacts are tracked in real-time and can be accessed either via the user interface
or the CLI.

To browse artifacts through the CLI, use the following command:

```bash
dstack artifacts list <run-name>
```

To download artifacts locally, use the following command:

```bash
dstack artifacts download <run-name>
```

[//]: # (TODO: Add screenshots)

[//]: # (TODO: Tell about stopping and restarting workflows)

[//]: # (TODO: Add a link to the CLI reference)

[//]: # (TODO: Add a link to Providers Reference)