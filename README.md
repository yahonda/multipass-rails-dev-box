# multipass-rails-dev-box

You can run rails-dev-box on M1 mac using Multipass.

# How to build "rails-dev-box"

1. Download [Multipass](https://multipass.run)
2. Clone this repository
  ```
  % git clone https://github.com/yahonda/multipass-rails-dev-box.git
  % cd multipass-rails-dev-box
  ```
3. Launch Multipass box
  ```shell
  % multipass launch 22.04 -d 20G --name rails-dev-box --cloud-init ./cloud-init.yaml --timeout 600
  ```
4. Login to Multipass box
  ```shell
  % multipass shell rails-dev-box
  ```
5. You can access the "rails-dev-box"
  ```shell
  ubuntu@rails-dev-box:~$
  ```