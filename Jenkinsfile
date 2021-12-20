pipeline {
  agent any
  stages {
    stage('Assessment') {
      parallel {
        stage('Assessment') {
          steps {
            echo 'Analyze build details sent from Wiser Workflow'
            echo 'Request No : REQST0001012  Customer Name : XYZ Company  Instance : PROD'
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
            sleep 5
            echo 'Initializing the backend...  Initializing provider plugins... - Finding hashicorp/aws versions matching "~> 3.27"... - Installing hashicorp/aws v3.27.0... - Installed hashicorp/aws v3.27.0 (signed by HashiCorp)  Terraform has created a lock file .terraform.lock.hcl to record the provider selections it made above. Include this file in your version control repository so that Terraform can guarantee to make the same selections by default when you run "terraform init" in the future.  Terraform has been successfully initialized!  You may now begin working with Terraform. Try running "terraform plan" to see any changes that are required for your infrastructure. All Terraform commands should now work.  If you ever set or change modules or backend configuration for Terraform, rerun this command to reinitialize your working directory. If you forget, other commands will detect it and remind you to do so if necessary.    terraform show # aws_instance.app_server: resource "aws_instance" "app_server" {     ami                          = "ami-830c94e3"     arn                          = "arn:aws:ec2:us-west-2:561656980159:instance/i-01e03375ba238b384"     associate_public_ip_address  = true     availability_zone            = "us-west-2c"     cpu_core_count               = 1     cpu_threads_per_core         = 1     disable_api_termination      = false     ebs_optimized                = false     get_password_data            = false     hibernation                  = false     id                           = "i-01e03375ba238b384"     instance_state               = "running"     instance_type                = "t2.micro"     ipv6_address_count           = 0     ipv6_addresses               = []     monitoring                   = false     primary_network_interface_id = "eni-068d850de6a4321b7"     private_dns                  = "ip-172-31-0-139.us-west-2.compute.internal"     private_ip                   = "172.31.0.139"     public_dns                   = "ec2-18-237-201-188.us-west-2.compute.amazonaws.com"     public_ip                    = "18.237.201.188"     secondary_private_ips        = []     security_groups              = [         "default",     ]     source_dest_check            = true     subnet_id                    = "subnet-31855d6c"     tags                         = {         "Name" = "ExampleAppServerInstance"     }     tenancy                      = "default"     vpc_security_group_ids       = [         "sg-0edc8a5a",     ]      credit_specification {         cpu_credits = "standard"     }      enclave_options {         enabled = false     }      metadata_options {         http_endpoint               = "enabled"         http_put_response_hop_limit = 1         http_tokens                 = "optional"     }      root_block_device {         delete_on_termination = true         device_name           = "/dev/sda1"         encrypted             = false         iops                  = 0         tags                  = {}         throughput            = 0         volume_id             = "vol-031d56cc45ea4a245"         volume_size           = 8         volume_type           = "standard"     } }'
            echo 'Infrastructure Provisioning - Complete'
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
            sleep 3
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
            sleep 2
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
            sleep 2
          }
        }

        stage('MSC Installation - 5.11 Service Pack 2') {
          steps {
            echo 'Deployment started and logs are kept in nohoup.out '
            echo 'nohup ansible-playbook -i /opt/customers/queu/hosts tasks/main_aws.yml -e"@inventories/aws/defaults/main.yml" -e"@/opt/customers/queu/env_vars.yml" -vv & - Running command'
            sleep 5
            echo 'TASK [msc-mds-master : start_platform - start MDS platform] ******************** task path: /opt/ansible/xmds/roles/msc-mds-master/tasks/start_platform.yml:2 Saturday 03 July 2021  10:57:52 +0000 (0:00:00.033)       0:00:29.773 *********  changed: [10.20.64.5] => {"changed": true, "cmd": "su -s /bin/sh msc -c \'source /opt/redkite/msc/centralMds/bin/setenv_runtime_server.txt && /opt/redkite/msc/centralMds/bin/start_platform.bash allqa\'", "delta": "0:00:00.081936", "end": "2021-07-03 10:57:52.382109", "rc": 0, "start": "2021-07-03 10:57:52.300173", "stderr": "", "stdout": "Processing command allqa\\nprocess name : fakexignite and process id : 15193\\nThe process is not running creating the pid file /tmp/var/run/mds/redkite_fakexignite.pid\\nstarted fakeXignite\\nprocess name : listingservice and process id : 15206\\nThe process is not running creating the pid file /tmp/var/run/mds/redkite_listingservice.pid\\nstarted listingservice\\nprocess name : benchmarkservice and process id : 15232\\nThe process is not running creating the pid file /tmp/var/run/mds/redkite_benchmarkservice.pid\\nstarted benchmarkservice\\nprocess name : tickservice and process id : 15261\\nThe process is not running creating the pid file /tmp/var/run/mds/redkite_tickservice.pid\\nstarted tickservice\\nprocess name : timelineservice and process id : 15290\\nThe process is not running creating the pid file /tmp/var/run/mds/redkite_timelineservice.pid\\nstarted timelineservice\\nprocess name : ravenpackmapping and process id : 15334\\nThe process is not running creating the pid file /tmp/var/run/mds/redkite_ravenpackmapping.pid\\nstarted ravenpackmapping", "stdout_lines": ["Processing command allqa", "process name : fakexignite and process id : 15193", "The process is not running creating the pid file /tmp/var/run/mds/redkite_fakexignite.pid", "started fakeXignite", "process name : listingservice and process id : 15206", "The process is not running creating the pid file /tmp/var/run/mds/redkite_listingservice.pid", "started listingservice", "process name : benchmarkservice and process id : 15232", "The process is not running creating the pid file /tmp/var/run/mds/redkite_benchmarkservice.pid", "started benchmarkservice", "process name : tickservice and process id : 15261", "The process is not running creating the pid file /tmp/var/run/mds/redkite_tickservice.pid", "started tickservice", "process name : timelineservice and process id : 15290", "The process is not running creating the pid file /tmp/var/run/mds/redkite_timelineservice.pid", "started timelineservice", "process name : ravenpackmapping and process id : 15334", "The process is not running creating the pid file /tmp/var/run/mds/redkite_ravenpackmapping.pid", "started ravenpackmapping"], "warnings": ["Consider using \'become\', \'become_method\', and \'become_user\' rather than running su"]} changed: [10.20.64.69] => {"changed": true, "cmd": "su -s /bin/sh msc -c \'source /opt/redkite/msc/centralMds/bin/setenv_runtime_server.txt && /opt/redkite/msc/centralMds/bin/start_platform.bash allqa\'", "delta": "0:00:00.076732", "end": "2021-07-03 10:57:52.394551", "rc": 0, "start": "2021-07-03 10:57:52.317819", "stderr": "", "stdout": "Processing command allqa\\nprocess name : fakexignite and process id : 1506\\nThe process is not running creating the pid file /tmp/var/run/mds/redkite_fakexignite.pid\\nstarted fakeXignite\\nprocess name : listingservice and process id : 1519\\nThe process is not running creating the pid file /tmp/var/run/mds/redkite_listingservice.pid\\nstarted listingservice\\nprocess name : benchmarkservice and process id : 1546\\nThe process is not running creating the pid file /tmp/var/run/mds/redkite_benchmarkservice.pid\\nstarted benchmarkservice\\nprocess name : tickservice and process id : 1573\\nThe process is not running creating the pid file /tmp/var/run/mds/redkite_tickservice.pid\\nstarted tickservice\\nprocess name : timelineservice and process id : 1604\\nThe process is not running creating the pid file /tmp/var/run/mds/redkite_timelineservice.pid\\nstarted timelineservice\\nprocess name : ravenpackmapping and process id : 1631\\nThe process is not running creating the pid file /tmp/var/run/mds/redkite_ravenpackmapping.pid\\nstarted ravenpackmapping", "stdout_lines": ["Processing command allqa", "process name : fakexignite and process id : 1506", "The process is not running creating the pid file /tmp/var/run/mds/redkite_fakexignite.pid", "started fakeXignite", "process name : listingservice and process id : 1519", "The process is not running creating the pid file /tmp/var/run/mds/redkite_listingservice.pid", "started listingservice", "process name : benchmarkservice and process id : 1546", "The process is not running creating the pid file /tmp/var/run/mds/redkite_benchmarkservice.pid", "started benchmarkservice", "process name : tickservice and process id : 1573", "The process is not running creating the pid file /tmp/var/run/mds/redkite_tickservice.pid", "started tickservice", "process name : timelineservice and process id : 1604", "The process is not running creating the pid file /tmp/var/run/mds/redkite_timelineservice.pid", "started timelineservice", "process name : ravenpackmapping and process id : 1631", "The process is not running creating the pid file /tmp/var/run/mds/redkite_ravenpackmapping.pid", "started ravenpackmapping"], "warnings": ["Consider using \'become\', \'become_method\', and \'become_user\' rather than running su"]}  PLAY RECAP ********************************************************************* 10.20.64.5                 : ok=106  changed=55   unreachable=0    failed=0    10.20.64.69                : ok=78   changed=45   unreachable=0    failed=0     Saturday 03 July 2021  10:57:52 +0000 (0:00:00.339)       0:00:30.112 *********  ===============================================================================  setup ------------------------------------------------------------------- 2.79s  ------------------------------------------------------------------------------ msc-mds-master : deploy_fakexignite_installer - unarchive  FakeXigniteServer archive --- 1.54s /opt/ansible/xmds/roles/msc-mds-master/tasks/deploy_fakexignite_installer.yml:7  msc-mds-master : deploy_mds_installer - unarchive MDS archive ----------- 1.25s /opt/ansible/xmds/roles/msc-mds-master/tasks/deploy_mds_installer.yml:7 ------- msc-mds-master : deploy_mdstesttools_installer - unarchive  MDSTestTools archive --- 0.91s'
            echo 'Deployment - Completed Successfully'
          }
        }

        stage('AVA Pre-Deployment Configuration') {
          steps {
            echo 'winRM to AVA Regional server'
            echo 'Append Customers AVA Servers details in AVA'
            echo 'AVA Configuration Complete'
            echo 'Pre-Configuration Completed'
          }
        }

        stage('AVA Installation') {
          steps {
            echo 'Uncomment AVA roles in tasks/main_aws.yml'
            echo 'Re-run the deployment - nohup ansible-playbook -i /opt/customers/queu/hosts tasks/main_aws.yml -e"@inventories/aws/defaults/main.yml" -e"@/opt/customers/queu/env_vars.yml" -vv &'
            echo 'AVA Installation Complete'
          }
        }

        stage('Post-Deployment Configuration') {
          steps {
            echo 'Users Creating in ActOne using Command line ---- Completed'
            echo 'System Configuration Updated in Actone System Configuration, Internal URL and User Sync ---- Completed'
            echo 'Product Installation ---- Completed'
            input(message: 'I certify that Surveil-X solution has been install and verified sucessfully', id: '126', ok: 'Approve')
            echo 'Change is Updated and Closed in Wiser'
            echo 'Service Request in Wiser Closed Successfully'
          }
        }

        stage('SSL Configuration') {
          steps {
            echo 'Installed SSL certificate for the customer and enable port 443 from server.xml'
          }
        }

      }
    }

    stage('Testing') {
      parallel {
        stage('Testing') {
          steps {
            echo 'Validation to be performed by PS Team'
          }
        }

        stage('Approval by PS Team') {
          steps {
            echo 'Requesting Certification'
            input(message: 'I certify that Surveil-X solution has been install and verified successfully', id: '127', ok: 'Approve')
            echo 'Accepted Updated in Service Request'
          }
        }

        stage('Publish Report') {
          steps {
            echo 'Change is Updated and Closed in Wiser'
            echo 'Service Request in Wiser Closed Successfully'
            echo 'Email Stakeholders Deployment Completed Successfully'
          }
        }

      }
    }

    stage('Documentation') {
      steps {
        echo 'Handover Documents Shared with PM and all stakeholders in pdf format'
      }
    }

  }
}