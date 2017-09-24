# drone_test for image ansible/centos7-ansible
docker run --rm \
  -e DRONE_COMMIT_AUTHOR=tazgong \
  -e DRONE_COMMIT_AUTHOR_EMAIL=tazgong@gmail.com \
  -e PLUGIN_SSH_KEY=~/.ssh/taz-key-pair-apseoul-ansible.pem \
  -e PLUGIN_BRANCH=master \
  -e PLUGIN_REMOTE=git@github.com:tazgong/test_drone.git \
  -e PLUGIN_FORCE=false \
  -v /workspace/devops/drone/drone_test/:/var/git \
  -w /var/git \
  -p 2222:22 \
  appleboy/drone-git-push


  docker run --rm \
  -e DRONE_COMMIT_AUTHOR=tazgong \
  -e DRONE_COMMIT_AUTHOR_EMAIL=tazgong@gmail.com \
  -e PLUGIN_SSH_KEY=~/.ssh/my-first-keypair.pem \
  -e PLUGIN_BRANCH=master \
  -e PLUGIN_REMOTE=git@alpinestartup.com:alpinestartup.git \
  -e PLUGIN_FORCE=false \
  -v /workspace/devops/drone:/data \
  -w /data \
  appleboy/drone-git-push

  docker run --rm \
  -e DRONE_COMMIT_AUTHOR=tazgong \
  -e DRONE_COMMIT_AUTHOR_EMAIL=tazgong@gmail.com \
  -e PLUGIN_SSH_KEY=@~/.ssh/my-first-keypair \
  -e PLUGIN_BRANCH=master \
  -e PLUGIN_REMOTE=git@alpinestartup.com:alpinestartup.git \
  -e PLUGIN_FORCE=false \
  -v /workspace/devops/drone/drone_test:/data \
  -w /data \
  appleboy/drone-git-push

drone secret add \
-repository tazgong/drone_test \
-image appleboy/drone-git-push \
-name git_push_ssh_key \
-value @{HOME}/.ssh/my-first-keypair

drone secret add \
--repository tazgong/drone_test \
--name git_push_ssh_key \
--value @${HOME}/.ssh/my-first-keypair \
--image appleboy/drone-git-push

drone secret remove tazgong/drone_test GIT_PUSH_SSH_KEY


