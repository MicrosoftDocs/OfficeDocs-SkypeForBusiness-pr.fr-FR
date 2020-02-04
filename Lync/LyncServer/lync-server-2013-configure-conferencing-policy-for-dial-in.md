---
title: 'Lync Server 2013 : Configuration de la stratégie de conférence rendez-vous'
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
ms.openlocfilehash: 107c5fcf4b341c652cd4044fe47f4b650cf5adb4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739344"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-conferencing-policy-for-dial-in-in-lync-server-2013"></a>Configuration de la stratégie de conférence rendez-vous dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-03-21_

Une stratégie de conférence est un paramètre de compte d’utilisateur qui spécifie les modalités de la conférence pour les participants. Vous pouvez créer des stratégies de conférence avec une étendue de site ou d’utilisateur. Les paramètres de stratégie de conférence englobent de nombreux aspects de la planification de la conférence et de la participation. Plusieurs paramètres de stratégies de conférence prennent en charge la conférence rendez-vous pour les participants. Lorsque vous configurez une conférence rendez-vous, vous devez vérifier que ces champs sont correctement définis pour votre organisation, et vous devez les modifier uniquement en cas de nécessité.

Vérifiez les champs suivants dans votre stratégie de conférence :

  - **Permettre aux participants d’inviter des utilisateurs**   anonymes ce paramètre permet aux organisateurs de la réunion d’inviter des participants anonymes (non authentifiés) aux réunions. Ce paramètre est facultatif pour les conférences rendez-vous. Ce paramètre est sélectionné par défaut dans la stratégie de conférence globale par défaut.

  - **Activer les conférences**   rendez-vous RTC ce paramètre permet aux utilisateurs d’accéder à la partie audio d’une conférence en composant un numéro de téléphone PSTN. Ce paramètre est requis pour les conférences rendez-vous. Ce paramètre est sélectionné par défaut dans la stratégie de conférence globale par défaut.

  - **Permettre aux participants anonymes d’appeler**   ce paramètre permet aux utilisateurs anonymes déjà joints à la réunion d’appeler un numéro de téléphone pour se connecter à la partie audio de la Conférence. Ce paramètre est facultatif pour les conférences rendez-vous. Ce paramètre n’est pas sélectionné par défaut dans la stratégie de conférence globale par défaut.

  - **Permettre aux participants non activés pour les appels vocaux d’entreprise de composer**   ce paramètre permet aux participants et aux organisateurs d’une réunion qui ne sont pas activés pour les appels sortants dans un numéro de téléphone pour accéder à la partie audio de la Conférence. Le numéro de téléphone est autorisé en fonction de la politique vocale affectée à l’organisateur. Ce paramètre n’est pas sélectionné par défaut dans la stratégie de conférence globale par défaut. La valeur par défaut du paramètre est Disabled.
    
    <div>
    

    > [!NOTE]  
    > Pour activer cette fonctionnalité, un organisateur de la réunion qui n’est pas activé pour voix entreprise doit avoir reçu une stratégie vocale appropriée pour autoriser les appels sortants d’une conférence organisée par cet utilisateur. Une stratégie vocale peut être affectée à un utilisateur qui n’est pas activé pour voix entreprise via Lync Server Management Shell. Si une stratégie vocale n’est pas explicitement attribuée à l’utilisateur, la stratégie de voix du site est utilisée pour autoriser la demande de numérotation. S’il n’y a aucune stratégie de voix du site, la stratégie vocale globale est utilisée.&nbsp;

    
    </div>

La procédure décrite dans cette section explique comment modifier une stratégie de conférence. Pour plus d’informations sur la configuration de tous les paramètres définissant l’utilisation des participants dans la stratégie de conférence par défaut, voir [créer ou modifier un ensemble de paramètres de configuration de réunion dans Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md). Pour plus d’informations sur la création d’une stratégie de conférence pour un utilisateur ou un groupe d’utilisateurs spécifiques, voir [créer ou modifier une stratégie de conférence dans Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md). Pour obtenir la liste de tous les paramètres de stratégie de conférence disponibles, voir [référence des paramètres de stratégie de conférence pour Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).

<div>

## <a name="to-modify-the-conferencing-policy-for-dial-in"></a>Pour modifier la stratégie de conférence pour les appels entrants

1.  Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle **CS-ServerAdministrator** ou **CsAdministrator** .

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Conférences**.

4.  Dans l’onglet **stratégie de conférence** , double-cliquez sur un nom de stratégie de conférence pour ouvrir la boîte de dialogue Modifier la stratégie de **Conférence** .

5.  Vérifiez que les champs de la Conférence rendez-vous sont appropriés pour votre organisation, puis modifiez les paramètres le cas échéant.

6.  Cliquez sur **Valider**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

