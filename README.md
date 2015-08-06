==Criar Branch==
git branch -b nomeBranch
ou
git branch  nomeBranch
git checkout nomeBranch

=== Push Branch====
git push -u origin nomeBranch  // to be track
git branch --set-upstream-to=origin/NomeBranch   //to be track
git branch -vv  //ver branchs tracked


==Deletar Branch==
git branch -d nomeBranch
git push origin :newfeature   //DELETAR REMOTO
git branch -dr origin/branchname


==Merge===
git merge --no-ff ocorrencias
git mergetool
git merge abort

==Local Resetar Arquivo==
git checkout -- file/to/restore.html
git checkout .  /reseta todos arquivos
git co 30cda7e39f1a1e42109e97261b77992fc9301e82^ -- ./src/main/java/br/com/amil/portal/controller/common/usuario/bypass/rules/BeneficiarioRedirect.java

==Local Resetar Branch==
git reset --hard/keep HEAD origin/nomeBranch
git reset --hard/keep HEAD nomeBranch
git reset --hard origin/HEAD

==Revert==
git revert 2b504be
git reset/keep --hard 2be18d9   // nao fica gravado no historico


== GERENCIAMENTO BRANCH==
Ver ultimo commit de todas branchs
git branch -v

Ver branchs que ja foram mergeadas na branch atual
git branch --merged
git branch --no-merged



=======CORRIGINDO COMMIT=======
git commit --amend -m "Atualiza ultimo commit"

adicionar alguma mudanca ultimo commit
git add some/changed/file.ext
git commit --amend -m "commit message"


======GIT DIFF=====
git diff master..contact-form
git diff 0023cdd..fcd6199
git diff --word-diff=plain
git diff -w


====REBASE======
git rebase --abort

git rebase <new-base>
    Move the current branch’s commits to the tip of <new-base>, which can be either a branch name or a commit ID.
git rebase -i <new-base>
    Perform an interactive rebase and select actions for each commit.
git commit --amend
    Add staged changes to the most recent commit instead of creating a new one.
git rebase --continue
    Continue a rebase after amending a commit.
git rebase --abort
    Abandon the current interactive rebase and return the repository to its former state.
git merge --no-ff <branch-name>
    Force a merge commit even if Git could do a fast-forward merge. 

====TAG BRANCH=====
git tag -a nometag numeroComit    //taguear
git tag new old      // renomear tag  git tag -d old
git fetch --tags	
git push --tags
git checkout -b nomeBranch nomeTag 
git describe


===== deletar tag=========
git tag -d release01 
git push origin :refs/tags/release01 


git tag bar bar -m"original message" --force

====REVERTER ARQUIVO EXCLUIDO======
git co 30cda7e39f1a1e42109e97261b77992fc9301e82^ -- ./path/main.java

======GIT=============
git log --graph


=========LIST DELETED FILE==============
Get a list of the deleted files and copy the full path of the deleted file
git log --diff-filter=D --summary | grep delete

Execute the next command to find commit id of that commit and copy the commit id
git log --all -- FILEPATH

Show diff of deleted file
git show COMMIT_ID -- FILE_PATH

Remember, you can write output to a file using > like
git show COMMIT_ID -- FILE_PATH > deleted.diff


=============^M character============
windows
git config --global core.whitespace cr-at-eol




