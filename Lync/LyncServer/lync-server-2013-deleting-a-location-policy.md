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
ms.openlocfilehash: 2ea7f585e42164c8387853c7525cd0478eeb4db4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763246"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-a-location-policy-in-lync-server-2013"></a>Suppression d’une stratégie d’emplacement dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-10_

Dans Lync Server 2013, vous pouvez utiliser la stratégie d’emplacement pour appliquer les paramètres relatifs à la fonctionnalité améliorée 9-1-1 (E9-1-1) et aux paramètres d’emplacement des utilisateurs ou des contacts. La stratégie d’emplacement détermine si un utilisateur est activé pour E9-1-1 et, si oui, le comportement d’un appel d’urgence. Par exemple, vous pouvez utiliser la stratégie d’emplacement pour définir le numéro constituant un appel d’urgence (par exemple, 911 aux États-Unis), si la sécurité d’entreprise doit être automatiquement notifiée et la manière dont l’appel doit être routé.

Vous pouvez configurer des stratégies d’emplacement à partir du groupe de **Configuration réseau** dans Lync Server 2013 Control Panel. Le panneau de configuration de Lync Server vous permet d’afficher, de créer, de modifier ou de supprimer des stratégies d’emplacement. Pour supprimer une stratégie d’emplacement, procédez comme suit. Pour plus d’informations sur la création ou la modification de stratégies d’emplacement, voir [création ou modification d’une stratégie d’emplacement dans Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md).

<div>

## <a name="to-delete-a-location-policy"></a>Pour supprimer une stratégie d’emplacement

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **configuration du réseau** , puis sur **stratégie d’emplacement**.

4.  Dans la page de **stratégie d’emplacement** , sélectionnez la stratégie d’emplacement que vous voulez supprimer.
    
    <div>
    

    > [!NOTE]  
    > Vous pouvez supprimer plusieurs stratégies d’emplacement à la fois. Pour cela, appuyez sur CTRL et sélectionnez plusieurs stratégies tout en maintenant la touche CTRL enfoncée. Vous pouvez sélectionner toutes les <STRONG>stratégies dans le</STRONG> menu <STRONG>Edition</STRONG> .

    
    </div>

5.  Dans le menu **modifier** , cliquez sur **supprimer**.

6.  Cliquez sur **OK**.
    
    <div>
    

    > [!IMPORTANT]  
    > La stratégie d’emplacement global ne peut pas être supprimée. Si vous tentez de supprimer la stratégie globale, vous recevez un message d’avertissement indiquant que la stratégie sera réinitialisée à ses valeurs par défaut.

    
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

