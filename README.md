# Stop Dataflow Jobs Jenkins Pipeline

This is a Jenkins Pipeline script written in Groovy syntax that is designed to stop running Dataflow jobs that match certain criteria. This script is intended to be used in a Jenkins Pipeline, and assumes that the appropriate environment variables have been set up in Jenkins.

## How to Use

To use this script, you will need to create a new Jenkins Pipeline job and add this script to the Pipeline definition. The script requires two environment variables to be set:

- `SERVICE_ACCOUNT_KEY`: This is the ID of a Jenkins credential that contains a service account key file for a Google Cloud Platform service account. This service account should have permission to cancel Dataflow jobs in the target project.
- `PROJECT_ID`: This is the ID of the Google Cloud Platform project where the Dataflow jobs are running.

Once these environment variables have been set up in Jenkins, the Pipeline should be ready to run.

## What the Script Does

The script performs the following steps:

1. Activates the specified Google Cloud Platform service account by running `gcloud auth activate-service-account`.
2. Gets a list of running Dataflow jobs that match the specified criteria by running `gcloud dataflow jobs list`.
3. Filters the list of running jobs to those that were created more than one day ago and whose name starts with a specific prefix.
4. Cancels the selected jobs using `gcloud dataflow jobs cancel`.

The script is designed to be used in a Jenkins Pipeline, but could also be adapted for use in other environments with appropriate modifications.

## Contact

If you have any questions or feedback about this script, feel free to reach out to the script author through their GitHub profile.
