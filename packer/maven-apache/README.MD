## Packer AMI creation

- Validate the json template

    packer validate template.json
    
- Inspect your json template

    packer inspect template.json
    
- Build an AMI image

    packer build template.json
    
    Note: packer build template.json 2>&1 | sudo tee output.txt
    
- For getting the Instace-ID from output file

     tail -2 output.txt | head -2 | awk 'match($0, /ami-.*/) { print substr($0, RSTART, RLENGTH) }'
     
     or
     
     tail -2 output.txt | head -1 | awk -F ':' {'print $2}'
