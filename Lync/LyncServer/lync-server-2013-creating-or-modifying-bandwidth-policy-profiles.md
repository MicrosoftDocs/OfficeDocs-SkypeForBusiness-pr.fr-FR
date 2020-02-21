---
title: 'Lync Server 2013 : création ou modification des profils de stratégie de bande passante'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying bandwidth policy profiles
ms:assetid: 08a2e18f-9b0d-4a2f-aa14-13bbf79ec745
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520945(v=OCS.15)
ms:contentKeyID: 48183336
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c46ec104972eff34f73825fbb384259fc6eb4ba
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213250"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-bandwidth-policy-profiles-in-lync-server-2013"></a>Création ou modification des profils de stratégie de bande passante dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-15_

La stratégie de bande passante utilisée dans le cadre du contrôle d’admission des appels (CAC) permet de définir des restrictions de bande passante pour des modes bien précis. Dans Microsoft Lync Server 2013, seules les modalités audio et vidéo peuvent se voir affecter des limites de bande passante. Vous pouvez définir des restrictions de bande passante et de session globales. Vous pouvez utiliser le panneau de configuration Lync Server pour créer, modifier ou supprimer un profil de conteneur pour ces stratégies. Chaque profil de stratégie de bande passante peut être associé à un ou plusieurs sites réseau. Effectuez les procédures suivantes pour créer ou modifier un profil de stratégie de bande passante. Pour supprimer un profil de stratégie de bande passante, consultez [la rubrique Suppression des profils de stratégie de bande passante réseau dans Lync Server 2013](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)

<div>

## <a name="to-create-a-new-bandwidth-policy-profile"></a>Pour créer un profil de stratégie de bande passante

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Stratégie de bande passante**.

4.  Dans la page **Stratégie de bande passante**, cliquez sur **Nouveau**.

5.  Dans **Nouveau profil de stratégie de bande passante**, tapez un nom dans le champ **Nom**. Ce nom doit être unique parmi tous les profils de stratégie de bande passante.

6.  Dans le champ **Limite audio**, tapez une valeur numérique. Cette valeur, exprimée en kbps, représente la bande passante maximale à allouer pour toutes les connexions audio.

7.  Entrez une valeur numérique dans le champ **Limite de session audio**. Cette valeur, exprimée en kbps, représente la bande passante maximale à allouer pour une connexion audio. Cette valeur doit être égale ou supérieure à 40.

8.  Entrez une valeur numérique dans le champ **Limite vidéo**. Cette valeur, exprimée en kbps, représente la bande passante maximale à allouer pour toutes les connexions vidéo.

9.  Entrez une valeur numérique dans le champ **Limite de session vidéo**. Cette valeur, exprimée en kbps, représente la bande passante maximale à allouer pour une connexion vidéo. Cette valeur doit être égale ou supérieure à 100.

10. (Facultatif) Tapez une valeur dans le champ **Description** pour fournir plus d’informations sur ce profil de stratégie de bande passante, car son nom ne suffit pas à le décrire.

11. Cliquez sur **Valider**.
    
    <div>
    

    > [!NOTE]  
    > La création d’un nouveau profil de stratégie de bande passante n’applique pas automatiquement les restrictions de bande passante. Vous devez d’abord associer le profil de stratégie à un site. Pour plus d’informations sur l’Association d’un profil de stratégie à un site, voir <A href="lync-server-2013-creating-or-modifying-network-sites.md">création ou modification de sites réseau dans Lync Server 2013</A>.

    
    </div>

</div>

<div>

## <a name="to-modify-a-bandwidth-policy-profile"></a>Pour modifier un profil de stratégie de bande passante

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Configuration réseau**, puis sur **Stratégie de bande passante**.

4.  Dans la page **Stratégie de bande passante**, cliquez sur le profil de stratégie de bande passante que vous souhaitez modifier.

5.  Dans le menu **Edition**, cliquez sur **Afficher les détails**.

6.  Dans la page **Modifier le profil de stratégie de bande passante**, modifiez les champs comme il convient (pour plus d’informations, voir la section « Pour créer un profil de stratégie de bande passante » plus haut dans cette rubrique).

7.  Cliquez sur **Valider**.
    
    <div>
    

    > [!NOTE]  
    > Lorsque vous modifiez le profil de stratégie de bande passante, celui-ci met immédiatement à jour les restrictions de bande passante de tous les sites réseau qui lui sont associés.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Suppression des profils de stratégie de bande passante réseau dans Lync Server 2013](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)  


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

