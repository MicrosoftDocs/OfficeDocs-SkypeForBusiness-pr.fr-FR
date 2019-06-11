---
title: 'Lync Server 2013 : Configuration de la stratégie de mobilité'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring mobility policy
ms:assetid: 595536e0-9bb3-49a3-8d13-1a77351ebc62
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690018(v=OCS.15)
ms:contentKeyID: 48184204
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7f71252064cef521058aba17a3c220a948e23c7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838203"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-mobility-policy-in-lync-server-2013"></a>Configuration de la stratégie de mobilité dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-13_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Lync Server 2013 fournit des stratégies de mobilité qui déterminent qui peut utiliser les fonctionnalités de mobilité, les appels via le bureau, la voix sur IP (VoIP) ou la vidéo, et si l’accès WiFi est requis pour les appels VoIP ou la vidéo. La fonction d’appel via le bureau permet à un utilisateur mobile de passer et de recevoir des appels sur un téléphone mobile en utilisant un numéro de téléphone professionnel à la place du numéro de téléphone mobile. Cette fonctionnalité empêche la partie appelée de voir le numéro de téléphone mobile de l’appelant et permet à un utilisateur d’éviter les frais d’appel sortants. La configuration de VoIP et de la vidéo permet aux utilisateurs de recevoir et de passer des appels et de la vidéo VoIP. Paramètres de l’utilisation WiFi définit si l’appareil d’un utilisateur est tenu d’utiliser un réseau WiFi sur un réseau de données cellulaires.

Par défaut, la mobilité, les appels via le bureau et les fonctions VoIP et vidéo sont activées. Les paramètres permettant d’exiger le Wi-Fi pour les appels voix et vidéo sont désactivés. Les administrateurs peuvent déterminer qui a accès à ces fonctionnalités en exécutant une cmdlet. Vous pouvez désactiver les options dans le monde entier, par site ou par utilisateur.

Pour pouvoir utiliser les fonctionnalités de mobilité et l’appel via le bureau, les utilisateurs doivent respecter les conditions préalables suivantes:

  - Les utilisateurs doivent être activés pour Lync Server 2013.

  - Les utilisateurs doivent être activés pour voix entreprise.

  - Une stratégie de mobilité doit être affectée aux utilisateurs et l’option **EnableMobility** est définie sur true.

Pour que les utilisateurs puissent utiliser un appel via le bureau, ils doivent respecter les deux conditions préalables supplémentaires suivantes:

  - Les utilisateurs doivent être disposant d’une politique vocale dont l’option **activer la sonnerie simultanée des téléphones** est activée.

  - Une stratégie de mobilité doit être affectée aux utilisateurs et l’option **EnableOutsideVoice** est définie sur true.

<div>


> [!NOTE]  
> Les utilisateurs qui ne sont pas activés pour voix entreprise peuvent utiliser leurs appareils mobiles pour passer des appels voix sur IP (VoIP) Lync vers Lync ou participer à des conférences à l’aide du lien Cliquer pour rejoindre sur leurs appareils mobiles, si vous attribuez ces utilisateurs aux options appropriées pour la politique vocale. Pour plus d’informations, reportez-vous à <A href="lync-server-2013-defining-your-mobility-requirements.md">définition de vos exigences de mobilité pour Lync Server 2013</A>.



</div>

Pour plus d’informations sur l’activation des utilisateurs pour Lync Server 2013, voir [désactiver ou réactiver un compte d’utilisateur pour Lync server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md). Pour plus d’informations sur l’activation des utilisateurs pour Enterprise Voice, voir [activer les utilisateurs d’Enterprise Voice dans Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md). Pour plus d’informations sur la configuration des options de stratégie vocale, voir [modifier une stratégie vocale et configurer les enregistrements d’utilisation RTC dans Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md).

<div>

## <a name="to-modify-global-mobility-policy"></a>Pour modifier la stratégie de mobilité globale

1.  Ouvrez une session sur n’importe quel ordinateur sur lequel Lync Server Management Shell et OCSCore sont installés en tant que membre du rôle CsAdministrator.

2.  Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Désactivez l’accès à la mobilité et aux appels via votre bureau. À partir de la ligne de commande, tapez :
    
        Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
    
    <div>
    

    > [!NOTE]  
    > Vous pouvez désactiver les appels via le mode de fonctionnement sans désactiver l’accès à la mobilité. Toutefois, vous ne pouvez pas désactiver la mobilité sans désactiver la fonction d’appel via le mode de fonctionnement.

    
    </div>

</div>

<div>

## <a name="to-modify-mobility-policy-by-site"></a>Pour modifier la stratégie de mobilité par site

1.  Ouvrez une session sur n’importe quel ordinateur sur lequel Lync Server Management Shell et OCSCore sont installés en tant que membre du rôle CsAdministrator.

2.  Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Créez une stratégie de niveau de site, puis désactivez VoIP et la vidéo, et activez l’option exiger une connexion audio et vidéo par site. À partir de la ligne de commande, tapez :
    
        New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $False -RequireWiFiForIPAudio $True -RequireWiFiForIPVideo $True

</div>

<div>

## <a name="to-modify-mobility-policy-by-user"></a>Pour modifier la stratégie de mobilité par utilisateur

1.  Ouvrez une session sur n’importe quel ordinateur sur lequel Lync Server Management Shell et OCSCore sont installés en tant que membre du rôle CsAdministrator.

2.  Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Créez des stratégies de mobilité au niveau utilisateur, puis désactivez la mobilité et les appels via votre bureau. À partir de la ligne de commande, tapez :
    
        New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
    
    Vous pouvez désactiver les appels via le mode de fonctionnement sans désactiver l’accès à la mobilité. Toutefois, vous ne pouvez pas désactiver la mobilité sans désactiver la fonction d’appel via le mode de fonctionnement.
    
    Par exemple :
    
        New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity -MobileUser1@contoso.com -PolicyName Tag:disableOutsideVoice

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Désactiver ou réactiver le compte d’utilisateur pour Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  
[Activer les utilisateurs d’Enterprise Voice dans Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md)  
[Modifier une stratégie vocale et configurer les enregistrements d’utilisation RTC dans Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  


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

