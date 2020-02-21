---
title: 'Lync Server 2013 : suppression d’une stratégie d’emplacement'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting a location policy
ms:assetid: 8ca9ba10-f45f-435a-b39c-519d251e9085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688125(v=OCS.15)
ms:contentKeyID: 49733724
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc554d24bc93b81969832c9d8d2b034d071760bf
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202490"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deleting-a-location-policy-in-lync-server-2013"></a>Suppression d’une stratégie d’emplacement dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-10_

Dans Lync Server 2013, vous pouvez utiliser la stratégie d’emplacement pour appliquer les paramètres liés à la fonctionnalité Enhanced 9-1-1 (E9-1-1) et aux paramètres de localisation pour les utilisateurs ou les contacts. La stratégie d’emplacement détermine si un utilisateur peut avoir recours au système E9-1-1 et, le cas échéant, le comportement d’un appel d’urgence. Par exemple, la stratégie d’emplacement permet de définir le numéro d’appel d’urgence (par exemple 911 aux États-Unis, 15 en France), de déterminer si le service de sécurité de l’entreprise doit être automatiquement averti et comment l’appel doit être acheminé.

Vous pouvez configurer des stratégies d’emplacement à partir du groupe **Configuration réseau** dans le panneau de configuration Lync Server 2013. Dans le panneau de configuration Lync Server, vous pouvez afficher, créer, modifier ou supprimer des stratégies d’emplacement. Utilisez les procédures suivantes pour supprimer une stratégie d’emplacement. Pour plus d’informations sur la création ou la modification de stratégies d’emplacement, reportez-vous à [la rubrique création ou modification d’une stratégie d’emplacement dans Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md).

<div>

## <a name="to-delete-a-location-policy"></a>Pour supprimer une stratégie d’emplacement

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Stratégie d’emplacement**.

4.  Dans la page **Stratégie d’emplacement**, sélectionnez la stratégie d’emplacement que vous souhaitez supprimer.
    
    <div>
    

    > [!NOTE]  
    > Vous pouvez supprimer plusieurs stratégies d’emplacement à la fois. Pour cela, appuyez sur Ctrl et tout en maintenant cette touche enfoncée, sélectionnez plusieurs stratégies. Ou, pour sélectionner toutes les stratégies, cliquez sur <STRONG>Sélectionner tout</STRONG> dans le menu <STRONG>Edition</STRONG>.

    
    </div>

5.  Dans le menu **Edition**, cliquez sur **Supprimer**.

6.  Cliquez sur **OK**.
    
    <div>
    

    > [!IMPORTANT]  
    > Vous ne pouvez pas supprimer la stratégie d’emplacement globale. Si vous tentez de supprimer cette stratégie vous obtiendrez un message d’erreur et les valeurs par défaut de cette stratégie seront rétablies.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Création ou modification d’une stratégie d’emplacement dans Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md)  
[Affichage des informations de stratégie d’emplacement dans Lync Server 2013](lync-server-2013-viewing-location-policy-information.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

