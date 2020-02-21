---
title: 'Lync Server 2013 : affichage des informations de stratégie d’emplacement'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing location policy information
ms:assetid: 14e41bcb-ea0a-49c2-99b3-1f61fc34416d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520954(v=OCS.15)
ms:contentKeyID: 48183489
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ebd92944d02cf899ad6da60a586cd5ec24e9aa8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211220"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="viewing-location-policy-information-in-lync-server-2013"></a>Affichage des informations de stratégie d’emplacement dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Dans Lync Server 2013, vous pouvez utiliser la stratégie d’emplacement pour appliquer les paramètres liés à la fonctionnalité Enhanced 9-1-1 (E9-1-1) et aux paramètres de localisation pour les utilisateurs ou les contacts. La stratégie d’emplacement détermine si un utilisateur peut avoir recours au système E9-1-1 et, le cas échéant, le comportement d’un appel d’urgence. Par exemple, la stratégie d’emplacement permet de définir le numéro d’appel d’urgence (par exemple 911 aux États-Unis, 15 en France), de déterminer si le service de sécurité de l’entreprise doit être automatiquement averti et comment l’appel doit être acheminé.

Vous pouvez configurer des stratégies d’emplacement à partir du groupe **Configuration réseau** dans le panneau de configuration Lync Server 2013. Dans le panneau de configuration Lync Server, vous pouvez afficher, créer, modifier ou supprimer des stratégies d’emplacement. Utilisez les procédures suivantes pour afficher des informations sur les stratégies d’emplacement. Pour plus d’informations sur la création ou la modification de stratégies d’emplacement, reportez-vous à [la rubrique création ou modification d’une stratégie d’emplacement dans Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md).

<div>

## <a name="to-view-information-about-a-location-policy"></a>Pour afficher des informations sur une stratégie d’emplacement

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Stratégie d’emplacement**.

4.  Dans la page **Stratégie d’emplacement**, sélectionnez la stratégie d’emplacement que vous souhaitez modifier.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.
    
    <div>
    

    > [!NOTE]  
    > Vous ne pouvez afficher des informations que sur une seule stratégie d’emplacement à la fois.

    
    </div>

Une stratégie unique, appelée Globale, existe par défaut. Il n’est pas possible de supprimer ou de renommer cette stratégie. Vous pouvez cependant la modifier. Cette stratégie s’applique à tous les utilisateurs et contacts, sauf si vous créez des stratégies de site ou par utilisateur. Les stratégies par utilisateur doivent être appliquées à des utilisateurs spécifiques.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Création ou modification d’une stratégie d’emplacement dans Lync Server 2013](lync-server-2013-creating-or-modifying-a-location-policy.md)  
[Créer des stratégies d’emplacement dans Lync Server 2013](lync-server-2013-create-location-policies.md)  
[Création ou modification d’un site réseau dans Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md)  


[New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy)  
[Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy)  
[Remove-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsLocationPolicy)  
[Get-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsLocationPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

