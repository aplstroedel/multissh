#!/usr/bin/env bash
OPTIND=1
while getopts "t:c:hr" options
do
 case "$options" in
  t) set -f
     IFS=' '
     target=($OPTARG);;
  r) root=true;;
  c) cmd=$OPTARG;;
  h) printf '%s\n' 'usage: -t=target[param], -r=root, -c=cmd[param]';;
 esac
done

if [[ -z "$root" ]]
then
 for x in "${target[@]}"
 do
  ssh -t "${x}" "${cmd}"
 done
elif [[ "$root" == true ]]
then
 echo 'password?'
 read -s password
 for x in "${target[@]}"
 do
  ssh "${x}" "(echo $password) | su - root -c '${cmd[@]}'"
 done
 unset root
fi
