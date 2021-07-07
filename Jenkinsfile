pipeline {
  agent any
  stages {
    stage('Assessment') {
      parallel {
        stage('Assessment') {
          steps {
            echo 'Analyze build details sent from Wiser Workflow'
          }
        }

        stage('Checks Files') {
          steps {
            echo 'Check if all the files are present'
          }
        }

        stage('Deconstruction') {
          steps {
            echo 'File will be parsed using Python and individual units will be created (sizing information, Product details, Application Configuration Details, Credentials etc) '
          }
        }

        stage('Essential Dependencies ') {
          steps {
            echo 'Make sure all the essential binaries are present like JDK, Python, Ansible, curl, zip etc'
          }
        }

      }
    }

    stage('Infrastructure ') {
      parallel {
        stage('Infrastructure ') {
          steps {
            echo 'Pre-Provisioning Validation'
          }
        }

        stage('Terraform Plan') {
          steps {
            echo 'Run Terraform Plan'
          }
        }

        stage('DevOps Intervention') {
          steps {
            echo 'DevOps Team, need to give approval to Infrastructure Spinoff'
            input(message: 'Do you wish to proceed with Infrastructure Deployment', id: '123', ok: 'Approve')
          }
        }

        stage('Provision Infrastructure') {
          steps {
            echo 'Terraform Apply - Started'
            echo 'Connecting to AWS Cloud'
            echo 'Infrastructure Provisioning - In Progress '
            echo 'Infrastructure Provisioning - Completed'
          }
        }

        stage('Validate Infrastructure ') {
          steps {
            echo 'Validating Infra - In Progress'
            echo 'Validating Infra - Complete'
            echo 'Publish Report and Email Stakeholders'
          }
        }

        stage('Publish Report') {
          steps {
            echo 'Publish Report and store all variables in central location for population Deployment files'
          }
        }

      }
    }

    stage('Dependencies') {
      parallel {
        stage('Dependencies') {
          steps {
            echo 'Node Enrollments, Dependencies Installation'
          }
        }

        stage('Node Enrollement') {
          steps {
            echo 'Enroll New Nodes with Ansible Master Node'
            echo 'Enrollment Completed'
          }
        }

        stage('Dependencies Installation') {
          steps {
            echo 'Installing JDK 1.8'
            echo 'Installing Python'
          }
        }

      }
    }

    stage('Monitoring Solutions') {
      parallel {
        stage('Monitoring Solutions') {
          steps {
            echo 'Monitoring and Cloud agents Deployment'
          }
        }

        stage('Cloudwatch') {
          steps {
            echo 'Install AWS CloudWatch Agents'
          }
        }

        stage('Nagios Enrollement') {
          steps {
            echo 'Installing NCPA'
            echo 'Enrolling Nodes with Nagios Solution'
          }
        }

      }
    }

    stage('Pre-Deployment') {
      parallel {
        stage('Handover') {
          steps {
            echo 'Assessment of Infrastructure provisioned and its upstream connectivity'
          }
        }

        stage('DevOps Handoff') {
          steps {
            input(message: 'I approve Solution Provisioned along with Monitoring agents streaming capabilities', id: '124', ok: 'Accept')
            echo 'Service Request - Updated'
            echo 'Publish Report for AppOps team with details like, nodes, IP, whitelisting, FQDN, Appstream, DB details, News and MDS servers.'
            echo 'PPS Updated'
          }
        }

        stage('AppOps Takeover') {
          steps {
            echo 'AppOps Team check all elements related to Product Deployment has been provisioned'
            input(message: 'I have validated all the necessary prerequisites are in place before starting deployment', id: '125', ok: 'Accept')
            echo 'Service Request Updated'
            echo 'Infrastructure accepted. Handover Completed and stakeholders are emailed'
          }
        }

      }
    }

    stage('Deployment') {
      parallel {
        stage('Deployment') {
          steps {
            echo 'Starting Deployment'
          }
        }

        stage('Create Customer Namespace') {
          steps {
            echo 'Create customer folders in /opt/customer in regional ansible Deployment server ----- Complete'
            echo 'Create hosts and env_vars.yml ----  ------ Complete'
            echo 'Release package is present in /opt/ansible/msc<version> check  ------ Complete'
            echo 'ansible.cfg check ------ Complete'
            echo 'Comment AVA deployment task in roles and save the file'
            sleep 10
          }
        }

        stage('MSC Installation - 5.10 Patch 8') {
          steps {
            echo 'Deployment started and logs are kept in nohoup.out '
            echo 'nohup ansible-playbook -i /opt/customers/queu/hosts tasks/main_aws.yml -e"@inventories/aws/defaults/main.yml" -e"@/opt/customers/queu/env_vars.yml" -vv & - Running command'
            sleep 10
            echo 'Deployment - Completed Successfully'
          }
        }

        stage('AVA Pre-Deployment Configuration') {
          steps {
            echo 'winRM to AVA Regional server'
            echo 'Append Customers AVA Servers details in AVA'
            echo 'AVA Configuration Complete'
            echo 'Uncomment AVA roles in tasks/main_aws.yml'
            echo 'Re-run the deployment - nohup ansible-playbook -i /opt/customers/queu/hosts tasks/main_aws.yml -e"@inventories/aws/defaults/main.yml" -e"@/opt/customers/queu/env_vars.yml" -vv &'
            echo 'AVA Installation Complete'
          }
        }

      }
    }

  }
}