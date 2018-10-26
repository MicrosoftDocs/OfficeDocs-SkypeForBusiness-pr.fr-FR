---
title: 'Lync Server 2013 : Installation de Windows PowerShell 3.0'
TOCTitle: Installation de Windows PowerShell 3.0
ms:assetid: d87bf21e-0a43-41cb-8fdc-626cedec8538
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205328(v=OCS.15)
ms:contentKeyID: 49299013
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Installation de Windows PowerShell 3.0 pour Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Pour bien déployer Lync Server 2013, vous devrez utiliser Windows PowerShell 3.0 sur chaque ordinateur de votre topologie Lync Server.

Désormais, pour les systèmes exécutant Windows Server 2012 ou Windows Server 2012 R2, vous n’avez besoin de réaliser aucune opération. Vous pouvez passer à l’étape suivante du déploiement, car PowerShell 3.0 est fourni avec ces systèmes d’exploitation.

> [!IMPORTANT]  
> En revanche, pour les systèmes exécutant Windows Server 2008 R2 SP1, vous devrez installer PowerShell 3.0 avant Lync Server 2013 ou rien ne fonctionnera. Pour installer PowerShell 3.0, reportez-vous à <a href="http://go.microsoft.com/fwlink/p/?linkid=329800">Windows Management Framework 3.0</a>. Il s’agit d’un lien direct vers la page de téléchargement de PowerShell 3.0 et les informations relatives à son installation réussie.

Une fois que vous l’avez terminée ou si vous souhaitez juste vérifier certains points avant de poursuivre le déploiement Lync Server, vous pourrez confirmer très simplement la présence de PowerShell 3.0 sur un serveur si vous procédez comme suit :

1.  Sur le serveur à vérifier, choisissez **Démarrer** et cliquez sur **Tous les programmes**, **Accessoires**, **Windows PowerShell**, puis **Windows PowerShell**.

2.  Dans la console Windows PowerShell, saisissez la commande suivante dans l’invite de commande, puis appuyez sur ENTRÉE :
    
        Get-Host | Select-Object Version

3.  Si Windows PowerShell 3.0 est installé, vous obtiendrez l’affichage suivant :
    
        Version
        -------
        3.0

