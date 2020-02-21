---
title: 'Lync Server 2013 : désactiver un utilisateur pour voix entreprise'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disable a user for Enterprise Voice
ms:assetid: 462002d8-21df-4d77-bf7f-4d059d6a4bb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688043(v=OCS.15)
ms:contentKeyID: 49733635
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fdcc6f69280357730e34f987f3c197db6950c285
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197597"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="disable-a-user-for-enterprise-voice-in-lync-server-2013"></a>Désactivation d’un utilisateur pour voix entreprise dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-21_

Utilisez la procédure suivante pour désactiver voix entreprise pour un compte d’utilisateur qui est activé pour Lync Server 2013.

<div>

## <a name="to-disable-a-user-account-for-enterprise-voice"></a>Pour désactiver un compte d’utilisateur pour voix entreprise

1.  Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.

4.  Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM (Security Accounts Manager, Gestionnaire de comptes de sécurité), de l’adresse SIP ou de l’URI (Uniform Resource Identifier) de ligne du compte d’utilisateur que vous souhaitez activer, puis cliquez sur **Rechercher**.

5.  Dans le tableau, cliquez sur le compte d’utilisateur que vous souhaitez activer pour voix entreprise.

6.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

7.  Dans la page **Modifier l’utilisateur Lync Server**, sous **Téléphonie**, cliquez sur l’option de votre choix à l’exception de **Voix Entreprise**.
    
    <div>
    

    > [!NOTE]  
    > Pour empêcher un utilisateur d’effectuer des appels audio ou vidéo à l’aide de Lync, sous <STRONG>téléphonie</STRONG>, cliquez sur <STRONG>audio/vidéo désactivé</STRONG>.

    
    </div>

8.  Cliquez sur **Valider**.

L’utilisateur ne peut plus utiliser la fonctionnalité voix entreprise.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Activer les utilisateurs pour voix entreprise dans Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md)  


[Gestion de voix entreprise pour les utilisateurs dans Lync Server 2013](lync-server-2013-managing-enterprise-voice-for-users.md)  
[Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

