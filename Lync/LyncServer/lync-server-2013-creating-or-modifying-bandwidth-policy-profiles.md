---
title: 'Lync Server 2013: création ou modification de profils de stratégie de bande passante'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Creating or modifying bandwidth policy profiles
ms:assetid: 08a2e18f-9b0d-4a2f-aa14-13bbf79ec745
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520945(v=OCS.15)
ms:contentKeyID: 48183336
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 38f44d759a77fea03b285d2e1af10838d508a6ba
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831762"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-bandwidth-policy-profiles-in-lync-server-2013"></a>Création ou modification des profils de stratégie de bande passante dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-15_

Dans le cadre du contrôle d’admission des appels (CAC), une stratégie de bande passante est utilisée pour définir des limitations de bande passante pour certaines modalités. Dans Microsoft Lync Server 2013, seules les modalités d’audio et de vidéo peuvent être affectées par des limitations de bande passante. Vous pouvez définir les limites générales de bande passante et les limites de session. Vous pouvez utiliser le panneau de configuration de Lync Server pour créer, modifier ou supprimer un profil de conteneur pour ces stratégies. Chaque profil de stratégie de bande passante peut être associé à un ou plusieurs sites réseau. Pour créer ou modifier un profil de stratégie de bande passante, procédez comme suit. Pour supprimer un profil de stratégie de bande passante, reportez-vous à [suppression des profils de stratégie de bande passante réseau dans Lync 2013 Server](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)

<div>

## <a name="to-create-a-new-bandwidth-policy-profile"></a>Pour créer un profil de stratégie de bande passante

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **configuration du réseau** , puis sur **stratégie de bande passante**.

4.  Dans la page **stratégie de bande passante** , cliquez sur **nouveau**.

5.  Dans **nouveau profil de stratégie de bande passante**, tapez un nom dans le champ **nom** . Ce nom doit être unique parmi tous les profils de stratégie de bande passante.

6.  Dans le champ **limite audio** , entrez une valeur numérique. Cette valeur correspond au nombre maximal de bande passante à allouer pour toutes les connexions audio, exprimée en kbps.

7.  Entrez une valeur numérique dans le champ **limite de session audio** . Cette valeur correspond au volume maximal de bande passante à allouer pour une connexion audio individuelle, exprimée en kbps. Cette valeur doit être 40 ou une version ultérieure.

8.  Entrez une valeur numérique dans le champ **limite vidéo** . Cette valeur correspond au volume maximal de bande passante à allouer pour toutes les connexions vidéo, exprimée en kbps.

9.  Entrez une valeur numérique dans le champ **limite de session vidéo** . Cette valeur correspond au volume maximal de bande passante à allouer pour une connexion vidéo individuelle, exprimée en kbps. Cette valeur doit être 100 ou une version ultérieure.

10. Facultatif Tapez une valeur dans le champ **Description** pour fournir des informations supplémentaires sur le profil de la stratégie de bande passante qui ne peut pas être exprimé uniquement par le nom.

11. Cliquez sur **Valider**.
    
    <div>
    

    > [!NOTE]  
    > La création d’un profil de stratégie de bande passante n’applique pas automatiquement les restrictions de bande passante. Vous devez d’abord associer le profil de la stratégie à un site. Pour plus d’informations sur l’Association d’un profil de stratégie à un site, voir <A href="lync-server-2013-creating-or-modifying-network-sites.md">création ou modification de sites réseau dans Lync Server 2013</A>.

    
    </div>

</div>

<div>

## <a name="to-modify-a-bandwidth-policy-profile"></a>Pour modifier le profil d’une stratégie de bande passante

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **configuration du réseau** , puis sur **stratégie de bande passante**.

4.  Dans la page **stratégie de bande passante** , cliquez sur le profil de la stratégie de bande passante que vous voulez modifier.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

6.  Dans la page **modifier le profil de la stratégie de bande passante** , modifiez les champs si nécessaire (pour plus d’informations, consultez la section «pour créer un profil de stratégie de bande passante» plus haut dans cette rubrique).

7.  Cliquez sur **Valider**.
    
    <div>
    

    > [!NOTE]  
    > Lorsque vous modifiez le profil de la stratégie de bande passante, il met à jour immédiatement les limites de bande passante pour tous les sites réseau associés à ce profil de stratégie de bande passante.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Supprimer des profils de stratégie de bande passante réseau dans Lync Server 2013](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)  


[Configurer le contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-configure-call-admission-control.md)  
[New-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  
[Set-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  
[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

