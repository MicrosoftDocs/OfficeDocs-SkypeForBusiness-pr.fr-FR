---
title: 'Lync Server 2013 : configuration de la stratégie de conférence pour les appels entrants'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure conferencing policy for dial-in
ms:assetid: 9bf926d6-0248-4352-98c3-9c5a333debbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398810(v=OCS.15)
ms:contentKeyID: 48184979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33f84ec3cb900b4283f30d67e318ab10d3625326
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204930"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-conferencing-policy-for-dial-in-in-lync-server-2013"></a>Configurer la stratégie de conférence pour les appels entrants dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-03-21_

Une stratégie de conférence est un paramètre de compte d’utilisateur qui spécifie les modalités de la conférence pour les participants. Vous pouvez créer des stratégies de conférence avec une étendue de site ou d’utilisateur. Les paramètres de stratégie de conférence englobent de nombreux aspects de la planification de la conférence et de la participation. Plusieurs paramètres de stratégies de conférence prennent en charge la conférence rendez-vous pour les participants. Lorsque vous configurez une conférence rendez-vous, vous devez vérifier que ces champs sont correctement définis pour votre organisation, et vous devez les modifier uniquement en cas de nécessité.

Vérifiez les champs suivants dans votre stratégie de conférence :

  - **Autoriser les participants à inviter des utilisateurs**   anonymes ce paramètre permet aux organisateurs de réunions d’inviter des participants anonymes (c’est-à-dire, non authentifiés) à des réunions. Ce paramètre est facultatif pour la conférence rendez-vous. Il est sélectionné par défaut dans la stratégie de conférence globale par défaut.

  - **Activer la Conférence**   rendez-vous PSTN ce paramètre permet aux utilisateurs de rejoindre la partie audio d’une conférence en appelant le réseau RTC. Ce paramètre est obligatoire pour la conférence rendez-vous. Il est sélectionné par défaut dans la stratégie de conférence globale par défaut.

  - **Autoriser les participants anonymes à composer**   ce paramètre permet aux utilisateurs anonymes qui sont déjà joints à la réunion de se connecter à un numéro de téléphone pour rejoindre la partie audio de la Conférence. Ce paramètre est facultatif pour la conférence rendez-vous. Il n’est pas sélectionné par défaut dans la stratégie de conférence globale par défaut.

  - **Autoriser les participants non activés pour voix entreprise à composer**   ce paramètre permet aux participants à la réunion et aux organisateurs qui ne sont pas activés pour l’accès à distance à un numéro de téléphone de participer à la partie audio de la Conférence. Celui-ci est autorisé en fonction de la stratégie de voix assignée de l’organisateur. Il n’est pas sélectionné par défaut dans la stratégie de conférence globale par défaut. Sa valeur par défaut est désactivée.
    
    <div>
    

    > [!NOTE]  
    > Pour activer cette fonctionnalité, l’organisateur de la réunion qui n’est pas activé pour Enterprise Voice doit disposer d’une stratégie de voix appropriée qui leur est attribuée pour autoriser des appels sortants à partir d’une conférence organisée par cet utilisateur. Une stratégie de voix peut être affectée à un utilisateur qui n’est pas activé pour voix entreprise à partir de Lync Server Management Shell. Si aucune stratégie de voix n’a été attribuée à l’utilisateur, la stratégie de voix du site est utilisée pour autoriser la demande d’appel sortant. S’il n’existe aucune stratégie de voix de site, la stratégie de voix globale est utilisée.&nbsp;

    
    </div>

La procédure de cette section explique comment modifier la stratégie de conférence. Pour plus d’informations sur la configuration de tous les paramètres qui définissent l’expérience des participants dans la stratégie de conférence par défaut, voir [Create or Modify a collection of meeting Configuration Settings in Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md). Pour plus d’informations sur la création d’une stratégie de conférence pour un utilisateur ou un groupe d’utilisateurs spécifique, voir [Create or Modify a Conferencing Policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md). Pour obtenir la liste de tous les paramètres de stratégie de conférence disponibles, consultez la rubrique [référence des paramètres de stratégie de conférence pour Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).

<div>

## <a name="to-modify-the-conferencing-policy-for-dial-in"></a>Pour modifier la stratégie de conférence rendez-vous

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou membre du rôle **Cs-ServerAdministratorr** ou **CsAdministrator**.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Conférence**.

4.  Sous l’onglet **Stratégie de conférence**, double-cliquez sur un nom de stratégie de conférence pour ouvrir la boîte de dialogue **Modifier la stratégie de conférence**.

5.  Vérifiez que les champs de la conférence rendez-vous correspondent à votre organisation et modifiez les paramètres, le cas échéant.

6.  Cliquez sur **Valider**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

