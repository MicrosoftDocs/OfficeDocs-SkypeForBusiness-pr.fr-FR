---
title: 'Lync Server 2013 : Lync Server Management Shell'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server Management Shell
ms:assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398474(v=OCS.15)
ms:contentKeyID: 48184386
ms.date: 09/20/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfc4ab6a9c32a8b060308526fcdb1f1da403a9e3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186157"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-management-shell"></a>Lync Server 2013 Management Shell

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2017-09-20_

<div>


> [!NOTE]  
> La référence de cmdlet Skype entreprise a été déplacée vers docs.microsoft.com. Cliquez sur les liens ci-dessous pour accéder à la nouvelle page docs.microsoft.com. Le contenu est désormais ouvert et disponible pour les contributions de la Communauté via GitHub. Vous souhaitez contribuer ? Consultez le fichier Lisez-moi dans le référentiel ici :<A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A>



</div>

Microsoft Lync Server 2010 a introduit un grand ensemble de fonctionnalités nouvelles et améliorées par rapport à ce qui était disponible dans Microsoft Office Communications Server 2007 R2. Parmi les améliorations qui ont été apportées figure la façon dont vous pouvez gérer votre implémentation. Par exemple, il existe une nouvelle interface utilisateur, appelée panneau de configuration Lync Server, qui représente une grande équipe de la plupart des utilisateurs avec Microsoft Management Console. L’intégration de Windows PowerShell est une autre amélioration majeure de la facilité de gestion.

Windows PowerShell vous permet de gérer les applications Microsoft à partir de la ligne de commande. Il comporte un environnement de ligne de commande, des commandes spécifiques aux produits et un langage de script complet. Windows PowerShell a été introduit pour la première fois en tant que version téléchargeable pour le système d’exploitation Windows en retard dans 2006, et a été incorporée comme interface de ligne de commande pour la gestion de Microsoft Exchange Server 2007. À partir de ce stade, il a continué à croître et il a été intégré dans la plupart des produits serveur Microsoft, les plus récents d’entre eux étant Microsoft Lync Server 2013. Lync Server 2010 introduit des applets de commande spécifiques aux produits de 550, que vous pouvez utiliser pour gérer tous les aspects de votre déploiement.

Les sections suivantes contiennent une liste des applets de commande et leurs descriptions. Ces informations sont aussi disponibles directement à partir de la ligne de commande. Il vous suffit de taper ce qui suit à l’invite de commandes Lync Server Management Shell :

    Get-Help <cmdlet name> -Full

Par exemple, pour accéder à l’aide depuis l’invite de commandes de l’applet de commande **New-CsVoicePolicy**, tapez les éléments suivants :

    Get-Help New-CsVoicePolicy -Full

Éléments à connaître sur Windows PowerShell dans Lync Server 2013 :

  - Pour exécuter les applets de commande Lync Server, ouvrez Lync Server Management Shell.
    
    <div>
    

    > [!WARNING]  
    > Si vous ouvrez une fenêtre Windows PowerShell au lieu de Lync Server Management Shell, par défaut, vous ne pourrez pas exécuter les applets de commande Lync Server. Pour exécuter les applets de commande Lync Server à partir de Windows PowerShell, tapez d’abord les éléments suivants à l’invite de commandes Windows PowerShell :<BR>Import-Module Lync

    
    </div>

  - Lync Server Management Shell est automatiquement installé sur chaque serveur frontal ou serveur Standard Edition Lync Server Enterprise Edition.

  - Des informations nouvelles et mises à jour, des exemples de scripts et de l’aide pour la mise en route et en savoir plus sur les applets de commande Windows PowerShell et Microsoft [https://go.microsoft.com/fwlink/p/?linkId=203150](https://go.microsoft.com/fwlink/p/?linkid=203150)lync Server 2013 sont disponibles sur le blog Lync Server Windows PowerShell.

</div>

<span> </span>

</div>

</div>

</div>

