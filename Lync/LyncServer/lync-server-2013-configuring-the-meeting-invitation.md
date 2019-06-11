---
title: 'Lync Server 2013: configuration de l’invitation à une réunion'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring the meeting invitation
ms:assetid: 7faa4797-0344-418b-9fa3-59dfb9c2baf7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398638(v=OCS.15)
ms:contentKeyID: 48184641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 014a42597e3df416d9e502eaaa90e2f1e71e35ec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838177"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-meeting-invitation-in-lync-server-2013"></a>Configurer l’invitation à une réunion dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-07-16_

Vous pouvez personnaliser les invitations aux réunions envoyées par le complément réunion en ligne pour Lync 2013 en incluant les éléments facultatifs suivants dans le corps de l’invitation à la réunion:

  - **Le logo de votre organisation** Ajoutez le logo de votre organisation aux invitations aux réunions à l’aide de l’option logo URL. Si des invitations de réunion seront envoyées à des personnes extérieures à votre organisation, l’image doit se trouver dans une URL disponible au public. Les formats d’image pris en charge sont GIF et JPG. Même si Lync Server 2013 stocke l’URL sans restrictions de taille sur l’image, pour des résultats optimisés, la taille maximale de l’image doit être de 30 pixels de hauteur de 188 pixels de large.

  - **Un lien d’aide ou d’assistance personnalisé** Ajoutez une URL pour l’aide ou le site Web de l’équipe de support technique de votre organisation. Si des invitations de réunion seront envoyées à des personnes extérieures à votre organisation, l’URL doit être publiquement disponible. La longueur d’URL maximale est d’au moins 1 Ko.

  - **Texte de renonciation légale** Ajoutez une URL pour le texte légal ou un avertissement qui sera affiché dans toutes les invitations à une réunion. Si des invitations de réunion seront envoyées à des personnes extérieures à votre organisation, l’URL doit être publiquement disponible. La longueur d’URL maximale est d’au moins 1 Ko.

  - **Texte de pied de page personnalisé** Ajoutez du texte qui sera affiché comme pied de page personnalisé dans l’invitation. La longueur maximale de texte pouvant être ajoutée est de 2 Ko.

Vous pouvez configurer ces options à l’aide de Lync Server Control Panel ou de Lync Server Management Shell.

<div>


**Pour personnaliser l’invitation à une réunion à l’aide du panneau de configuration de Lync Server**

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à n’importe quel ordinateur se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Conférence** , puis sur Configuration de la **réunion**.

4.  Dans la page **Configuration de la réunion**, cliquez sur **Nouveau**, puis effectuez l’une des opérations suivantes :
    
      - Pour créer une stratégie au niveau du site, cliquez sur **Configuration du site**. Dans le champ de recherche **Sélectionner un site**, tapez le nom du site (en totalité ou partiellement) pour lequel vous souhaitez définir des paramètres de participation aux réunions. Dans la liste des sites obtenus, cliquez sur le site voulu, puis sur **OK**.
    
      - Pour créer une stratégie au niveau du pool, cliquez sur **Configuration du pool**. Dans le champ de recherche **Sélectionner un service**, tapez le nom du service de pool (en totalité ou partiellement) pour lequel vous souhaitez définir des paramètres de participation aux réunions. Dans la liste des services obtenus, cliquez sur le pool de votre choix, puis sur **OK**.

5.  Effectuez l’une des opérations suivantes :
    
      - Dans le champ **URL du logo** , entrez l’URL de l’image de logo de votre organisation.
    
      - Dans le champ URL de l' **aide** , tapez l’URL du site d’aide ou de support de votre organisation.
    
      - Dans le champ **texte légal** , tapez l’URL du texte légal ou de l’exclusion de responsabilité que vous voulez inclure dans les invitations aux réunions.
    
      - Dans le champ de **texte de pied de page personnalisé** , tapez texte de pied de page de 2 Ko au maximum.

**Pour personnaliser l’invitation à une réunion à l’aide de Lync Server Management Shell**

1.  Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

2.  Exécutez l’applet de **CsMeetingConfiguration** ou **Set-CsMeetingConfiguration** pour créer ou configurer les options d’invitation à une réunion. Par exemple, exécutez :
    
        New-CsMeetingConfiguration -Identity site:Redmond -LogoURL "http://www.contoso.com/logo/contosobanner.gif" -HelpURL "http://www.contoso.com/support" -LegalURL "http://www.contoso.com/disclaimer" -CustomFooterText "Communications may be monitored or recorded."

</div>

</div>

<span> </span>

</div>

</div>

</div>

