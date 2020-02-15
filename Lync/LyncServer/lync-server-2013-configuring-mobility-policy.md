---
title: 'Lync Server 2013 : configuration de la stratégie de mobilité'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring mobility policy
ms:assetid: 595536e0-9bb3-49a3-8d13-1a77351ebc62
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690018(v=OCS.15)
ms:contentKeyID: 48184204
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6410e50a5e7d84de152b9a4e4bd1f962c5a3c9bd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008406"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-mobility-policy-in-lync-server-2013"></a>Configuration de la stratégie de mobilité dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-13_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Lync Server 2013 fournit des stratégies de mobilité qui déterminent qui peut utiliser les fonctionnalités de mobilité, l’appel via le bureau, la voix sur IP (VoIP) ou la vidéo, et si WiFi est requis pour la voix ou la vidéo. La fonctionnalité appeler via le bureau permet à un utilisateur mobile de passer et de recevoir des appels sur un téléphone mobile en utilisant un numéro de téléphone professionnel au lieu du numéro de téléphone mobile. Cette fonctionnalité empêche la partie appelée de voir le numéro de téléphone mobile de l’appelant et permet à un utilisateur d’éviter les frais d’appels sortants. La configuration de la VoIP et de la vidéo permet aux utilisateurs de recevoir et de passer des appels VoIP et de vidéo. Paramètres d’utilisation de WiFi définissez si l’appareil d’un utilisateur doit utiliser un réseau WiFi sur un réseau de données cellulaires.

Par défaut, la mobilité, l’appel via le bureau et les fonctionnalités VoIP et vidéo sont activées. Les paramètres permettant d’exiger WiFi pour VoIp et vidéo sont désactivés. Les administrateurs peuvent déterminer qui a accès à ces fonctionnalités en exécutant une applet de commande. Il est possible de désactiver les options globalement, par site ou par utilisateur.

Pour pouvoir utiliser les fonctionnalités de mobilité et d’Appel via le bureau, les utilisateurs doivent remplir les conditions préalables suivantes :

  - Les utilisateurs doivent être activés pour Lync Server 2013.

  - les utilisateurs doivent être activés pour Voix Entreprise.

  - une stratégie de mobilité dont l’option **EnableMobility** a la valeur True doit être assignée aux utilisateurs.

Pour pouvoir utiliser la fonctionnalité d’Appel via le bureau, les utilisateurs doivent remplir les deux conditions supplémentaires suivantes :

  - une stratégie de voix ayant l’option **Activer la sonnerie simultanée de téléphones** activée doit être assignée aux utilisateurs ;

  - une stratégie de mobilité dont l’option **EnableOutsideVoice** a la valeur True doit être assignée aux utilisateurs.

<div>


> [!NOTE]  
> Les utilisateurs qui ne sont pas activés pour voix entreprise peuvent utiliser leurs appareils mobiles pour passer des appels Lync à Lync VoIP (voix sur IP) ou participer à des conférences en utilisant le lien Cliquer pour rejoindre les appareils mobiles, si vous leur attribuez les options appropriées pour la stratégie de voix. Pour plus d’informations, reportez-vous à <A href="lync-server-2013-defining-your-mobility-requirements.md">la rubrique définition de vos besoins de mobilité pour Lync Server 2013</A>.



</div>

Pour plus d’informations sur l’activation des utilisateurs pour Lync Server 2013, reportez-vous à la rubrique désactiver ou réactiver [le compte d’utilisateur pour Lync server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md). Pour plus d’informations sur l’activation des utilisateurs pour voix entreprise, consultez la rubrique [activation des utilisateurs pour voix entreprise dans Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md). Pour plus d’informations sur la configuration des options de stratégie de voix, voir [modifier une stratégie de voix et configurer les enregistrements d’utilisation PSTN dans Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md).

<div>

## <a name="to-modify-global-mobility-policy"></a>Pour modifier la stratégie de mobilité globale

1.  Ouvrez une session sur un ordinateur sur lequel Lync Server Management Shell et OCSCore sont installés en tant que membre du rôle CsAdministrator.

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

3.  Désactivez globalement l’accès à la mobilité et l’Appel via le bureau.
    
        Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
    
    <div>
    

    > [!NOTE]  
    > Vous pouvez désactiver l’Appel via le bureau sans désactiver l’accès à la mobilité. En revanche, il est impossible de désactiver la mobilité sans également désactiver l’Appel via le bureau.

    
    </div>

</div>

<div>

## <a name="to-modify-mobility-policy-by-site"></a>Pour modifier la stratégie de mobilité par site

1.  Ouvrez une session sur un ordinateur sur lequel Lync Server Management Shell et OCSCore sont installés en tant que membre du rôle CsAdministrator.

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

3.  Créez une stratégie au niveau du site, puis désactivez VoIP et la vidéo, et activez l’entrée « WiFi » pour l’audio IP et la vidéo IP par site. Sur la ligne de commande, tapez :
    
        New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $False -RequireWiFiForIPAudio $True -RequireWiFiForIPVideo $True

</div>

<div>

## <a name="to-modify-mobility-policy-by-user"></a>Pour modifier la stratégie de mobilité par utilisateur

1.  Ouvrez une session sur un ordinateur sur lequel Lync Server Management Shell et OCSCore sont installés en tant que membre du rôle CsAdministrator.

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

3.  Créez des stratégies de mobilité au niveau de l’utilisateur et désactivez la mobilité et l’Appel via le bureau par utilisateur. Sur la ligne de commande, tapez :
    
        New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
    
    Vous pouvez désactiver l’Appel via le bureau sans désactiver l’accès à la mobilité. En revanche, il est impossible de désactiver la mobilité sans également désactiver l’Appel via le bureau.
    
    Par exemple :
    
        New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity -MobileUser1@contoso.com -PolicyName Tag:disableOutsideVoice

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Désactiver ou réactiver le compte d’utilisateur pour Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  
[Activer les utilisateurs pour voix entreprise dans Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md)  
[Modifier une stratégie de voix et configurer des enregistrements d’utilisation PSTN dans Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  


[Définition de la configuration requise pour la mobilité pour Lync Server 2013](lync-server-2013-defining-your-mobility-requirements.md)  


[New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy)  
[Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy)  
[Get-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy)  
[Grant-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy)  
[Remove-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

