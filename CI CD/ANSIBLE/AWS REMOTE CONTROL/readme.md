# Run following command to get EC2 instance public id and save in inventory file

```sh
aws ec2 describe-instances \
--query 'Reservations[*].Instances[*].PublicIpAddress' \
--filters "Name=tag:Project,Values=udacity" \
--output text >> inventory
```

# Run Playbook using your inventory file 
```sh
ansible-playbook main-remote.yml -i inventory --private-key udacity.pem
```