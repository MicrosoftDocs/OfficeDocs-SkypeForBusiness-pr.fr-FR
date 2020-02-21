---
title: 'Lync Server 2013 : configuration de l’invitation à la réunion'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the meeting invitation
ms:assetid: 7faa4797-0344-418b-9fa3-59dfb9c2baf7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398638(v=OCS.15)
ms:contentKeyID: 48184641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ceb06f7efc6f23ff040edb66282ed4dc246ca836
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191867"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-the-meeting-invitation-in-lync-server-2013"></a>Configuration de l’invitation à la réunion dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-07-16_

Vous pouvez personnaliser les invitations aux réunions envoyées par le complément de réunion en ligne pour Lync 2013 en incluant les éléments facultatifs suivants dans le corps de l’invitation à la réunion :

  - **Logo de votre organisation** Ajoutez le logo de votre organisation aux invitations aux réunions à l’aide de l’option URL du logo. Si des invitations à des réunions sont envoyées à des personnes extérieures à votre organisation, l’image doit se trouver à l’URL publiquement disponible. Les formats d’image pris en charge sont GIF et JPG. Bien que Lync Server 2013 stocke l’URL sans aucune restriction de taille sur l’image, pour obtenir de meilleurs résultats, la taille maximale de l’image doit être de 30 pixels de haut par 188 pixels de large.

  - **Un lien d’aide ou de support personnalisé** Ajoutez une URL pour le site Web de l’aide ou de l’équipe de support de votre organisation. Si des invitations à des réunions sont envoyées à des personnes extérieures à votre organisation, l’URL doit être publiquement disponible. La longueur maximale de l’URL est de 1 Ko.

  - **Texte de la clause d’exclusion de responsabilité légale** Ajoutez une URL pour le texte légal ou une clause d’exclusion de responsabilité qui s’affichera dans toutes les invitations à une réunion. Si des invitations à des réunions sont envoyées à des personnes extérieures à votre organisation, l’URL doit être publiquement disponible. La longueur maximale de l’URL est de 1 Ko.

  - **Texte de pied de page personnalisé** Ajouter du texte qui sera affiché sous la forme d’un pied de page personnalisé dans l’invitation. La longueur maximale du texte pouvant être ajouté est de 2 Ko.

Vous pouvez configurer ces options à l’aide du panneau de configuration Lync Server ou de Lync Server Management Shell.

<div>


**Pour personnaliser l’invitation à une réunion à l’aide du panneau de configuration Lync Server**

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Configuration de la réunion**.

4.  Dans la page **Configuration de la réunion**, cliquez sur **Nouveau**, puis effectuez l’une des opérations suivantes :
    
      - Pour créer une stratégie au niveau du site, cliquez sur **Configuration du site**. Dans le champ de recherche **Sélectionner un site**, tapez le nom du site (en totalité ou partiellement) pour lequel vous souhaitez définir des paramètres de participation aux réunions. Dans la liste des sites obtenus, cliquez sur le site voulu, puis sur **OK**.
    
      - Pour créer une stratégie au niveau du pool, cliquez sur **Configuration du pool**. Dans le champ de recherche **Sélectionner un service**, tapez le nom du service de pool (en totalité ou partiellement) pour lequel vous souhaitez définir des paramètres de participation aux réunions. Dans la liste des services obtenus, cliquez sur le pool de votre choix, puis sur **OK**.

5.  Effectuez l’une des opérations suivantes :
    
      - Dans le champ **URL du logo** , tapez l’URL de l’image du logo de votre organisation.
    
      - Dans le champ URL de l' **aide** , entrez l’URL du site d’aide ou de support de votre organisation.
    
      - Dans le champ **texte juridique** , tapez l’URL du texte ou de la clause d’exclusion de responsabilité que vous souhaitez inclure dans les invitations aux réunions.
    
      - Dans le champ de **texte de pied de page personnalisé** , tapez texte de pied de page, jusqu’à 2 Ko.

**Pour personnaliser l’invitation à une réunion à l’aide de Lync Server Management Shell**

1.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

2.  Exécutez la cmdlet **New-CsMeetingConfiguration** ou **Set-CsMeetingConfiguration** pour créer ou configurer les options d’invitation à la réunion. Par exemple, exécutez :
    
        New-CsMeetingConfiguration -Identity site:Redmond -LogoURL "http://www.contoso.com/logo/contosobanner.gif" -HelpURL "http://www.contoso.com/support" -LegalURL "http://www.contoso.com/disclaimer" -CustomFooterText "Communications may be monitored or recorded."

</div>

</div>

<span> </span>

</div>

</div>

</div>

