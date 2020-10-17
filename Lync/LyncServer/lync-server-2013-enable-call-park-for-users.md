---
title: 'Lync Server 2013 : activation du parcage d’appel pour les utilisateurs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Call Park for users
ms:assetid: 9430763f-3394-467c-9c6d-426bf761604e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398753(v=OCS.15)
ms:contentKeyID: 48184814
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9345cdf2665a5a02d04a372606b95111d870a727
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528781"
---
# <a name="enable-call-park-for-users-in-lync-server-2013"></a>Activer le parcage d’appel pour les utilisateurs dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-11_

Les utilisateurs ne peuvent pas parkiser les appels ou récupérer les appels parqués jusqu’à ce qu’ils soient activés pour le parcage d’appel dans la stratégie de voix.

<div>


> [!NOTE]  
> Par défaut, le parcage d’appel est désactivé pour tous les utilisateurs.



</div>

Vous pouvez activer le parcage d’appel au niveau de l’étendue globale ou de l’étendue du site ou de l’utilisateur. L’étendue d’utilisateur est prioritaire sur l’étendue du site et l’étendue du site est prioritaire sur l’étendue globale. Si vous avez plusieurs stratégies de voix, vérifiez toutes les stratégies pour activer le parcage d’appel, et pas seulement la stratégie globale.

<div>

## <a name="to-use-lync-server-control-panel-to-enable-call-park-for-users"></a>Pour utiliser le panneau de configuration Lync Server pour activer le parcage d’appel pour les utilisateurs

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe **RTCUniversalServerAdmins** ou membre du rôle d’administrateur **CsVoiceAdministrator**, **CsServerAdministrator** ou**CsAdministrator**.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**.

4.  Cliquez sur l’onglet **Stratégie de la voix**.

5.  Double-cliquez sur une stratégie de voix existante pour ouvrir la boîte de dialogue **Modifier la stratégie de voix**.

6.  Sous **Fonctionnalités d’appel**, sélectionnez **Activer le parcage d’appel**.

7.  Cliquez sur **OK** pour enregistrer la stratégie de voix.

</div>

<div>

## <a name="to-use-cmdlets-to-enable-call-park-for-users"></a>Pour utiliser des applets de commande afin d’activer le parcage d’appel pour les utilisateurs

1.  Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins, ou en tant que membre du rôle d’administrateur CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

3.  Générer
    
        Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
    
    Par exemple, pour activer le parcage d’appel pour la stratégie de voix globale par défaut :
    
        Set-CsVoicePolicy -EnableCallPark $true

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Création d’une stratégie de voix et configuration des enregistrements d’utilisation PSTN dans Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

