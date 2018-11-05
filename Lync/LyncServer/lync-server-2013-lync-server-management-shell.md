---
title: Lync Server Management Shell
TOCTitle: Lync Server Management Shell
ms:assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398474(v=OCS.15)
ms:contentKeyID: 49297453
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server Management Shell

 

_**Dernière rubrique modifiée :** 2016-12-08_

Par rapport à Microsoft Office Communications Server 2007 R2, Microsoft Lync Server 2010 fournit un ensemble complet de fonctionnalités nouvelles et améliorées. Parmi les améliorations qui ont été apportées figure la façon dont vous pouvez gérer votre implémentation. Par exemple, la nouvelle interface utilisateur, appelée Panneau de configuration Lync Server, constitue un grand pas en avant pour ceux qui sont habitués à utiliser la Microsoft Management Console. L’autre amélioration majeure qui renforce encore davantage la simplicité de gestion est l’intégration de Windows PowerShell.

Windows PowerShell vous permet de gérer les applications Microsoft depuis la ligne de commande. Il comporte un environnement de ligne de commande, des commandes spécifiques aux produits et un langage de script complet. Windows PowerShell a d’abord été intégré sous forme de version téléchargeable pour le système d’exploitation Windows fin 2006, et a été incorporé comme interface de ligne de commande afin de simplifier la gestion de Microsoft Exchange Server 2007. Depuis lors, il n’a cessé de se développer et a été intégré à la plupart des produits Microsoft Server, le plus récent d’entre eux étant Microsoft Lync Server 2013. Lync Server 2010 comprend presque 550 applets de commande spécifiques aux produits que vous pouvez utiliser pour gérer chaque aspect de votre déploiement.

Les sections suivantes contiennent une liste des applets de commande et leurs descriptions. Ces informations sont aussi disponibles directement à partir de la ligne de commande. Tapez simplement les éléments suivants à l’invite de commande Lync Server Management Shell :

    Get-Help <cmdlet name> -Full

Par exemple, pour accéder à l’aide depuis l’invite de commande de l’applet de commande **New-CsVoicePolicy**, tapez les éléments suivants :

    Get-Help New-CsVoicePolicy -Full

Éléments à retenir sur Windows PowerShell dans Lync Server 2013 :

  - Pour exécuter les applets de commande Lync Server, ouvrez Lync Server Management Shell.
    
    > [!WARNING]  
    > Si vous ouvrez une fenêtre Windows PowerShell à la place de Lync Server Management Shell, par défaut, vous ne pourrez pas exécuter les applets de commande Lync Server. Pour exécuter les applets de commande Lync Server à partir de Windows PowerShell, tapez d’abord les éléments suivants à l’invite de commande Windows PowerShell :<br />
    Import-Module Lync

  - Lync Server Management Shell est automatiquement installé sur chaque serveur Standard Edition ou serveur frontal Enterprise Edition Lync Server.

  - Toutes les informations nouvelles ou mises à jour, les exemples de scripts et l’aide vous permettant de commencer à utiliser les applets de commande Windows PowerShell et Microsoft Lync Server 2013, et d’en savoir plus sur celles-ci, sont disponibles sur le blog Windows PowerShell Lync Server, à l’adresse [http://go.microsoft.com/fwlink/?linkid=203150\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=203150%26clcid=0x40c).

