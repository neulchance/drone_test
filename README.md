# drone_test for image ansible/centos7-ansible

[centos]$ drone secret add --repository tazgong/drone_test --image appleboy/drone-git-push --name GIT_PUSH_SSH_KEY --value @${HOME}/.ssh/my-first-keypair
