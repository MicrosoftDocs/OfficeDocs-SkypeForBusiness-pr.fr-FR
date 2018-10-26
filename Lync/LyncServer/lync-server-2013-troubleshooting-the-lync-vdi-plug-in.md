---
title: "Résol. des pb du plug-in Lync VDI (Virtual Desktop Infrastructure) ds LS 2013"
TOCtitle: "Résol. des pb du plug-in Lync VDI (Virtual Desktop Infrastructure) ds LS 2013"
ms:assetid: 183c9449-b907-409c-b5ed-b02af3bd93ee
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204713(v=OCS.15)
ms:contentKeyID: 49296393
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Résolution des problèmes du plug-in Lync VDI (Virtual Desktop Infrastructure) dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-10_

## Résolution des problèmes liés à l’installation du plug-in Lync VDI (Virtual Desktop Infrastructure) sur un client léger

Si vous rencontrez des problèmes lors de l’installation du plug-in VDI sur un client léger, vérifiez les points suivants :

  - Assurez-vous que l’espace est suffisant dans le dossier que vous avez spécifié dans les variables système TEMP et TMP.

  - Assurez-vous que la protection en écriture est désactivée. Reportez-vous à la documentation du fabricant de votre périphérique pour en savoir plus.

## Résolution des problèmes liés au jumelage

Lorsque le jumelage du plug-in VDI échoue, l’icône du jumelage qui se trouve dans l’angle inférieur droit prend la forme d’un « X » rouge, comme ceci :

![Icône Lync VDI indiquant un jumelage réussi](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Icône Lync VDI indiquant un jumelage réussi")

Voici les raisons possibles des échecs, ainsi que les mesures que vous pouvez prendre pour y remédier.

  - **L’utilisateur a entré des informations d’identification incorrectes au moment de la connexion.**
    
    L’utilisateur doit se déconnecter de Lync et se reconnecter avec les informations d’identification appropriées. La boîte de dialogue de jumelage réapparaît et indique si le jumelage a réussi.

  - **Une autre instance du client Bureau à distance est en cours d’exécution.**
    
    Si vous utilisez une connexion Bureau à distance dans Windows, procédez ainsi :
    
    1.  Démarrez le Gestionnaire des tâches : appuyez sur **Alt+Ctrl+Suppr**, puis cliquez sur **Démarrer le Gestionnaire des tâches**.
    
    2.  Cliquez sur l’onglet **Processus** et recherchez tous les processus nommés **mstsc.exe** dans la liste.
    
    3.  Mettez chaque processus **mstsc.exe** en surbrillance et cliquez sur **Arrêter le processus**.
    
    4.  Démarrez une nouvelle session Bureau à distance et réessayez de vous connecter.

  - **Les fichiers nécessaires n’ont pas été installés correctement.**
    
    Une fois le plug-in installé sur l’ordinateur local, les fichiers suivants doivent se trouver sous C:\\Program Files\\Microsoft Office\\Office15 (ou la lettre de lecteur qui convient) :
    
      - LyncVdiPlugin.dll
    
      - UcVdi.dll
    
    Si des problèmes liés au jumelage VDI se sont produits, vérifiez que ces fichiers sont présents sur l’ordinateur local.

  - **Le client Lync s’exécute sur l’ordinateur local.**
    
    Pour utiliser le plug-in Lync VDI, aucun client Lync ne doit s’exécuter sur l’ordinateur local. Sinon, le jumelage échoue. Il est recommandé de ne pas installer le client Lync sur l’ordinateur local.

