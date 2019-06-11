---
title: 'Lync Server 2013: activer le parc d’appels pour les utilisateurs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable Call Park for users
ms:assetid: 9430763f-3394-467c-9c6d-426bf761604e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398753(v=OCS.15)
ms:contentKeyID: 48184814
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16538ba00571c429493a2bc0ce1ef14b0a331305
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831325"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-call-park-for-users-in-lync-server-2013"></a>Activer le parc d’appels pour les utilisateurs dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-11_

Les utilisateurs ne peuvent pas parcer les appels ou récupérer les appels en stationnement tant qu’ils sont activés pour le parc d’appels dans la politique vocale.

<div>


> [!NOTE]  
> Par défaut, le parc d’appels est désactivé pour tous les utilisateurs.



</div>

Vous pouvez activer le parc d’appels au niveau de l’étendue globale, ou à l’étendue du site ou l’étendue de l’utilisateur. L’étendue d’utilisateur est prioritaire sur l’étendue du site et l’étendue du site est prioritaire sur l’étendue globale. Si vous avez plusieurs stratégies vocales, passez en revue toutes les stratégies pour activer le parc d’appels, pas seulement la politique globale.

<div>

## <a name="to-use-lync-server-control-panel-to-enable-call-park-for-users"></a>Pour utiliser le panneau de configuration de Lync Server pour activer le parc d’appels pour les utilisateurs

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe **RTCUniversalServerAdmins** ou membre du rôle d’administrateur **CsVoiceAdministrator**, **CsServerAdministrator** ou **CsAdministrator**.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**.

4.  Cliquez sur l’onglet **Stratégie de la voix**.

5.  Double-cliquez sur une stratégie de voix existante pour ouvrir la boîte de dialogue **Modifier la stratégie de voix**.

6.  Sous **Fonctionnalités d’appel**, sélectionnez **Activer le parcage d’appel**.

7.  Cliquez sur **OK** pour enregistrer la stratégie de voix.

</div>

<div>

## <a name="to-use-cmdlets-to-enable-call-park-for-users"></a>Utiliser des cmdlets pour activer le parc d’appels pour les utilisateurs

1.  Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle d’administrateur CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.

2.  Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Exécutez :
    
        Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
    
    Par exemple, pour activer le parc d’appels pour la stratégie vocale globale par défaut:
    
        Set-CsVoicePolicy -EnableCallPark $true

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Créer une stratégie de voix et configurer les enregistrements d’utilisation RTC dans Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

