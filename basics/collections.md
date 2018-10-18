# Collections

In this section is described how Mimic manage requests for endpoints that are not part of the current project.

Mimic offers two differents solutions to manage this particular case:

- Mock button
- API forwarding

## Mock Button

When Mimic receive a request for a unknown endpoint the log line is marked in red:

![Error Log](../Images/error_log.png 'Error Log')

As shown on the image above the log contains a **Mock** button, clicking on it the endpoint details panel will be shown and you can create a new endpoint...

## API forwarding

Mimic can forward the request to the real service, to do it the project must have the inforamtion about the real service:

- Domain
- Path
- Port

You can set them during the project set up or opening the project details clicking on the menu icon on the top of the window and selecting _project settings_

![Project Setting](../Images/project_settings.png 'Project Setting')

The project settings popup allows you to set the information about your real service:

![Project Details](../Images/edit_project.png 'Project Details')
