---
title: 'Lync Server 2013: désactiver un utilisateur pour voix entreprise'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Disable a user for Enterprise Voice
ms:assetid: 462002d8-21df-4d77-bf7f-4d059d6a4bb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688043(v=OCS.15)
ms:contentKeyID: 49733635
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dabe378f07cbca263ba3b32257c310b01bd922c0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831389"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disable-a-user-for-enterprise-voice-in-lync-server-2013"></a>Désactiver un utilisateur pour voix entreprise dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-21_

Utilisez la procédure suivante pour désactiver Enterprise Voice pour un compte d’utilisateur activé pour Lync Server 2013.

<div>

## <a name="to-disable-a-user-account-for-enterprise-voice"></a>Pour désactiver un compte d’utilisateur pour voix entreprise

1.  À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.

4.  Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM (Security Accounts Manager), de l’adresse SIP (Session Initiation Protocol) ou de l’URI de ligne du compte d’utilisateur à activer, puis cliquez sur **Rechercher**.

5.  Dans la table, cliquez sur le compte d’utilisateur que vous souhaitez activer pour voix entreprise.

6.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

7.  Dans la page **modifier l’utilisateur de Lync Server** , sous **téléphonie**, cliquez sur une option sauf **entreprise voix**.
    
    <div>
    

    > [!NOTE]  
    > Pour empêcher un utilisateur de passer des appels audio ou vidéo à l’aide de Lync, sous <STRONG>téléphonie</STRONG>, cliquez sur <STRONG>audio/vidéo désactivé</STRONG>.

    
    </div>

8.  Cliquez sur **Valider**.

L’utilisateur ne peut plus utiliser la fonctionnalité voix entreprise.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Activer les utilisateurs d’Enterprise Voice dans Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md)  


[Gestion de voix entreprise pour les utilisateurs dans Lync Server 2013](lync-server-2013-managing-enterprise-voice-for-users.md)  
[Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

