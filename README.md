# Comment puis-je récupérer un commit perdu dans Git ?

## Chaque fois que le HEAD est modifié, il y aura une nouvelle entrée dans lereflog

## Essayez ceci, cela montrera tous les commits enregistrés dans git pendant une période de temps

    git reflog
## Trouvez le commit que vous voulez avec

    git log HEAD@{3}
    ou

    git log -p HEAD@{3}    
    
## Vérifiez ensuite si c'est le bon:

    git checkout HEAD@{3}
    
## Cela créera une tête détachée pour ce commit. Ajoutez et validez les modifications si nécessaire

    git status 
    git add
    git commit -m "temp_work" 
## Maintenant, si vous voulez restaurer le commit vers une branche, disons master, vous devrez nommer ce commutateur de branche master puis fusionner avec master.

    git branch temp
    git checkout master
    git merge temp
