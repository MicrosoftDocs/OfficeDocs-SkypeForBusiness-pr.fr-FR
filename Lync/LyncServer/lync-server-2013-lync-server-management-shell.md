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
ms.openlocfilehash: d519b647eae4937af10a38673803484a253baef7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742184"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-server-2013-management-shell"></a>Lync Server 2013 Management Shell

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2017-09-20_

<div>


> [!NOTE]  
> Référence sur les applets de la cmdlet Skype entreprise a été déplacée vers docs.microsoft.com. Cliquer sur les liens ci-dessous vous permet d’atteindre la nouvelle page docs.microsoft.com. Le contenu est désormais ouvert et est disponible pour les contributions de la Communauté par le biais de GitHub. Vous voulez participer ? Consultez le fichier README dans le référentiel Samples :<A href="https://github.com/microsoftdocs/office-docs-powershell">https://github.com/MicrosoftDocs/office-docs-powershell</A>



</div>

Microsoft Lync Server 2010 a introduit un grand nombre de fonctionnalités nouvelles et améliorées par rapport à ce qui était disponible dans Microsoft Office Communications Server 2007 R2. L’une des améliorations est le mode de gestion de votre implémentation. Par exemple, il existe une nouvelle interface utilisateur, appelée panneau de configuration de Lync Server, qui représente un important changement de l’utilisation de la plupart des personnes avec la console de gestion Microsoft. L’autre amélioration majeure de la gestion est l’inclusion de Windows PowerShell.

Windows PowerShell vous permet de gérer les applications Microsoft à partir de la ligne de commande. Il comporte un environnement de ligne de commande, des commandes spécifiques aux produits et un langage de script complet. Windows PowerShell s’est d’abord présenté comme une version téléchargeable du système d’exploitation Windows en retard dans 2006, et il a été intégré en tant qu’interface de ligne de commande pour la gestion de Microsoft Exchange Server 2007. À partir de ce point, il a continué de grandir et il a été intégré à la plupart des produits Microsoft Server, les plus récents d’eux étant Microsoft Lync Server 2013. Lync Server 2010 a présenté des applets de passe spécifiques à 550, que vous pouvez utiliser pour gérer chaque aspect de votre déploiement.

Les sections suivantes contiennent une liste des applets de commande et leurs descriptions. Ces informations sont aussi disponibles directement à partir de la ligne de commande. Tapez simplement ce qui suit dans l’invite de commandes de Lync Server Management Shell :

    Get-Help <cmdlet name> -Full

Par exemple, pour accéder à l’aide depuis l’invite de commande de l’applet de commande **New-CsVoicePolicy** tapez les éléments suivants :

    Get-Help New-CsVoicePolicy -Full

Éléments à connaître sur Windows PowerShell dans Lync Server 2013 :

  - Pour exécuter les applets de cmdlet Lync Server, ouvrez Lync Server Management Shell.
    
    <div>
    

    > [!WARNING]  
    > Par défaut, si vous ouvrez une fenêtre Windows PowerShell plutôt que Lync Server Management Shell, vous ne serez pas en mesure d’exécuter les applets de cmdlet de Lync Server. Pour exécuter les applets de commande Lync Server à partir de Windows PowerShell, commencez par taper la commande suivante à l’invite de commandes Windows PowerShell :<BR>Importer-module Lync

    
    </div>

  - Lync Server Management Shell est automatiquement installé sur chaque serveur frontal Lync Server Enterprise Edition ou Standard Edition Server.

  - Des informations nouvelles et mises à jour, des exemples de scripts et de l’aide pour la mise en route et en savoir plus sur les applets de cmdlet Windows PowerShell et Microsoft [https://go.microsoft.com/fwlink/p/?linkId=203150](https://go.microsoft.com/fwlink/p/?linkid=203150)Lync Server 2013 sont disponibles sur le blog Windows PowerShell de Lync Server.

</div>

<span> </span>

</div>

</div>

</div>

