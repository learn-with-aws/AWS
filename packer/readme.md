## Some Other Packer Information
Refe: https://devopscube.com/packer-tutorial-for-beginners/

## Ansible usecase

- Run ansible plabooks in Provisioners.

      "provisioners": [
          {
            "type": "ansible",
            "playbook_file": "./playbook.yml"
          }
        ]
        
- Extra args

      "provisioners": [
      {
        "type": "ansible",
        "extra_arguments": [
          "--connection=chroot",
          "--inventory-file=/mnt/packer-amazon-chroot"
        ],
        "playbook_file": "main.yml"
      }
    ]
    
## AMI additional EBS attachments

      "ami_block_device_mappings": [{
        "delete_on_termination": "true",
        "device_name": "/dev/sda1",
        "volume_size": 30
      }],
      "launch_block_device_mappings": [{
        "delete_on_termination": "true",
        "device_name": "/dev/sda1",
        "volume_size": 30
      }], 


## Sleep | timeOut

- Example 1

      {
        "type": "shell",
        "inline": ["sleep 10"]
      } 
      
- Example 2

      {
        "type": "shell",
        "script": "script.sh",
        "pause_before": "10s",
        "timeout": "10s"
      }

## Copy file

        {
            "type": "file",
            "source": "./scripts/ubuntu/welcome.txt",
            "destination": "/home/ubuntu/"
        }
        
## 
