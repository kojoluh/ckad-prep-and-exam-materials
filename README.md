# CKAD - Prep and Exam Materials

# Certified Kubernetes Application Developer (CKAD) Study Guide

Welcome to the comprehensive CKAD preparation repository! This collection of materials is designed to help you succeed in your journey to becoming a Certified Kubernetes Application Developer.

## 📚 What's Inside

- **Practice Labs**: Hands-on exercises covering all CKAD domains
- **Study Notes**: Detailed explanations of key concepts
- **Exam Tips**: Strategic advice for test day
- **Sample Questions**: Real-world scenario based questions
- **Command Reference**: Quick lookup for essential kubectl commands

## 🎯 Exam Domains

1. Application Design and Build (20%)
2. Application Deployment (20%) 
3. Application Observability and Maintenance (15%)
4. Application Environment, Configuration and Security (25%)
5. Services and Networking (20%)

## 🚀 Getting Started

1. Clone this repository
2. Review the study materials
3. Practice with hands-on labs
4. Test yourself with sample questions
5. Time your practice sessions

- ~1 month of general study with 3 days of exam prep
- 120 minute exam, had ~50 minutes after my first passthrough
- passed with a score of 91% (66% pass threshold)

## outline
- how to study
- the testing environment
- finesse guide

## how to study

- complete a course
  - 
- [killercoda.com](https://killercoda.com/login)
  - run all experiments and scenarios there
- [killer.sh](https://killer.sh/)
  - 2 free runs with exam purchase
  - 2 free runs with exam purchase
  - do ONCE (timed) then REVIEW
  - the explanations are very well done, read them all.
  - [UPDATE: july 2022](https://twitter.com/_killer_shell/status/1548205851940229120?s=20&t=O9b0xhvhWuaOwRVAkKsRzQ) now in a remote desktop like the updated exam!
- [killer coda scenarios](https://killercoda.com/killer-shell-cka)
  - do each one and read the explanations

## the testing environment
![interface](https://miro.medium.com/max/875/1*EzwMAPg4-XuBBWqt6WTmLQ.png)

[source: Kim Wuestkamp on itnext.io](https://itnext.io/cks-cka-ckad-changed-terminal-to-remote-desktop-157a26c1d5e)

- checkin process
  - ID check and camera scan
  - clean your testing area
  - one monitor
  - don't stress
- moved to remote desktop environment in Nov 2024
  - XFCE, Firefox
  - expect some lag
  - multiple terminals and browser tabs allowed
  - keyboard layout preserved
- copy/paste
  - right click menu
  - ctrl-shift-(c|v)
  - one-click copy from instructions (recommended to avoid typos)
  - copying from firefox will trigger a warning (and maybe miss a character)
- terminal
  - `kubectl` is pre-aliased to `k` with autocompletion
  - `.vimrc` is pre-set (no need to remember) `shiftwidth=2; expandtab=true; tabstop=2`
  - vscode and webstorm available as well [more here](https://docs.linuxfoundation.org/tc-docs/certification/lf-handbook2/exam-user-interface#virtual-machine-jsnad-and-jsnsd-exams-only)
  - `tmux` available but not necessary
- misc recommendations
  - use a big screen
  - hide the PSI top bar
  - maximize your comfort

## finesse guide

### mindset
- time is your most valuable resource, speed is your best friend
- be imperative first, declarative second

### `k create|run ... -h`
- copying yaml from docs is LAST RESORT
  - just make the thing with `k create|run`
  - add `... --dry-run=client -o yaml > resource.yaml` if you need to add things before apply
- use the `-h` option
  - tells you EXACTLY what can be created imperatively WITH EXAMPLES
  - menu increases in detail with base command

### understand [the k8s docs](https://kubernetes.io/docs/home/)
- remember important pages and examples
  - mentally bookmark templates that can't be created interactively (pv, pvc, netpol, etc.)
- ctrl-f `kind: <MY RESOURCE>` to quickly find example yaml
- use the [one-pager api reference](https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.24/) for specific details

### use shortnames
- never type out a full resource name if you can help it
  - cm -> configmap
  - pvc -> persistentvolumeclaim
  - ...
- check all shortnames with `k api-resources`

### aliases, functions, and variables
- memorize what you think you'll use

```{bash}
# IMHO must-haves

## create yaml on-the-fly faster
export do='--dry-run=client -o yaml'

## organize your files per question #
mkcd() { mkdir -p "$@" && cd "$@" ; }
```

```{bash}
# nice to haves

## create/destroy from yaml faster
alias kaf='k apply -f '
alias kdf='k delete -f '
alias kcf='k create -f '

## namespaces (poor man's `kubens`)
export nk='-n kube-system'
export n='-n important-ns' # set this as needed

## destroy things without waiting
export now='--grace-period 0 --force'
```

## 💡 Pro Tips

- Get comfortable with vim/nano for quick edits
- Practice kubectl imperative commands
- Master yaml indentation
- Learn to use kubectl explain
- Focus on speed and accuracy

## 🔗 Additional Resources

- [Official CKAD Curriculum](https://github.com/cncf/curriculum)
- [Kubernetes Documentation](https://kubernetes.io/docs/)
- [Linux Foundation CKAD Page](https://training.linuxfoundation.org/certification/certified-kubernetes-application-developer-ckad/)

## Credits

Author: Foster Kojo Luh
Email: luhfluh@gmail.com

## 🤝 Contributing

Feel free to contribute by:
- Adding practice questions
- Improving documentation
- Sharing exam tips
- Fixing errors

## 📝 License

This project is licensed under the MIT License - see the LICENSE file for details.

---
Good luck with your CKAD certification! Remember: Practice makes perfect! 🎉

