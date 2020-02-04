---
title: 'Lync Server 2013 : Définition de la configuration requise pour la mobilité'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your mobility requirements
ms:assetid: b7608335-cdeb-4aae-8e4b-d80c55f0d62b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690039(v=OCS.15)
ms:contentKeyID: 48185226
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2721f88ce703fe4c26fbc7a9a6cd02cdde6b14a8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762752"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-mobility-requirements-for-lync-server-2013"></a>Définition de la configuration requise pour la mobilité pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-14_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Pendant la phase de planification de la fonctionnalité de mobilité de Lync Server 2013, lorsque vous utilisez les clients mobiles Lync 2010 mobile et Lync 2013, vous prenez des décisions qui déterminent vos étapes de déploiement.

Voici les décisions que vous devez prendre en compte :

  - **Voulez-vous utiliser la découverte automatique pour les clients mobiles Lync ?**
    
    Si vous voulez prendre en charge la découverte automatique, vous devez créer des enregistrements DNS internes et externes, ajouter d’autres noms d’objet aux certificats sur les serveurs frontaux, les directeurs et le proxy inverse, puis modifier les règles de publication existantes. sur le proxy inverse. Pour plus d’informations, voir [Configuration requise pour la mobilité dans Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md). La découverte automatique permet aux utilisateurs de retrouver automatiquement les services Web Lync Server 2013 à partir de n’importe où, à l’intérieur ou à l’extérieur du réseau d’entreprise, sans entrer d’URL dans leurs paramètres d’appareil mobile.
    
    Si vous utilisez les paramètres manuels au lieu de la découverte automatique, les utilisateurs mobiles doivent entrer manuellement les URL suivantes dans leurs appareils mobiles :
    
      - https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/root pour l’accès externe
    
      - https://\<IntPoolFQDN\>/Autodiscover/Autodiscoverservice. svc/root pour l’accès interne
    
    Nous vous recommandons vivement d’utiliser la découverte automatique. Pour résoudre les problèmes, le principal recours aux paramètres manuels.

  - **Si vous décidez de prendre en charge la découverte automatique, êtes-vous prêt à mettre à jour les certificats du proxy inverse avec des noms de remplacement pour chaque domaine SIP ?**
    
    Si vous avez de nombreux domaines SIP, la mise à jour des certificats publics sur le proxy inverse peut devenir très onéreuse. Si tel est le cas, vous pouvez choisir d’implémenter la découverte automatique de manière à ce que la demande de service de découverte automatique initiale utilise HTTP sur le port 80, au lieu d’utiliser HTTPs sur le port 443. Toutefois, il ne s’agit pas de l’approche recommandée. Si vous décidez d’en choisir une autre, vous n’avez pas besoin de mettre à jour les certificats sur le proxy inverse, mais vous devez créer une règle de publication Web pour HTTP sur le port 80. Pour en savoir plus, voir [exigences techniques en matière de mobilité dans Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).

  - **Souhaitez-vous prendre en charge les clients mobiles Lync à la fois internes et externes au réseau d’entreprise, ou les clients de support technique uniquement à l’intérieur du réseau d’entreprise ?**
    
    Si vous voulez prendre en charge les clients mobiles internes et externes à votre réseau, les appareils mobiles peuvent accéder aux fonctionnalités de mobilité depuis n’importe quel emplacement. La configuration par défaut consiste à prendre en charge les clients internes et externes au réseau d’entreprise.
    
    Même si la configuration par défaut permet au trafic du client mobile de traverser le site externe, vous pouvez limiter le trafic client mobile au réseau d’entreprise interne. Lorsque vous restreignez le trafic vers le réseau interne, les utilisateurs peuvent utiliser les applications mobiles Lync sur leur appareil mobile uniquement lorsqu’elles se trouvent à l’intérieur du réseau.
    
    Pour les déploiements prenant en charge la mobilité à l’aide du service de mobilité MCX et de Lync 2010 mobile, vous exécutez l’applet **de passe Set-CsMcxConfiguration** . Pour définir la mobilité pour une utilisation interne uniquement, vous devez utiliser une commande semblable à ce qui suit :
    
        Set-CsMcxConfiguration -Identity site:Redmond -ExposedWebURL Internal
    
    <div>
    

    > [!NOTE]  
    > Aucune configuration supplémentaire n’est requise pour UCWA. UCWA n’a pas de configuration équivalente en interne.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > Si vous utilisez un serveur frontal ou une&nbsp;grappes frontale lync Server 2013, et <STRONG>que vous n’avez pas</STRONG> de serveurs&nbsp;frontaux 2010 Lync Server ou de pools frontal, <STRONG>il n’est pas nécessaire de disposer de la persistance basée sur le cookie</STRONG>. Si vous avez besoin de conserver un serveur frontal&nbsp;ou un pool frontal de lync Server 2010, les mêmes règles s’appliquent également à celle de lync Server 2010 pour la persistance basée sur les cookies.

    
    </div>

  - **Souhaitez-vous prendre en charge les notifications de transmission pour les appareils Apple iOS et Windows Phone ?**
    
    Si vous prenez en charge les notifications de transmission, les appareils Apple iOS et les téléphones Windows pris en charge reçoivent une notification d’événements qui se produisent lorsque l’application mobile est désactivée. Vous devez configurer votre serveur Edge pour qu’il dispose d’une relation de Fédération avec le service de notification Poussée de Lync Server sur le Cloud, qui se trouve dans Lync Online datacenter et qu’il exécute une cmdlet pour activer les notifications de transmission.
    
    Si vous voulez prendre en charge les notifications de transmission sur votre réseau Wi-Fi, en plus de prendre en charge les notifications de transmission sur les réseaux 3G ou les réseaux de données du fournisseur d’appareils mobiles, vous devez ouvrir le port 5223 sortant sur votre réseau Wi-Fi d’entreprise. La prise en charge des notifications de transmission sur le réseau Wi-Fi prend en charge les appareils mobiles qui utilisent uniquement le Wi-Fi et les appareils mobiles présentant une mauvaise réception intérieur.
    
    <div>
    

    > [!IMPORTANT]  
    > L’ouverture du port TCP 5223 est requise uniquement lors de la prise en charge des appareils Apple exécutant le client mobile Lync 2010.

    
    </div>
    
    Si vous ne prenez pas en charge les notifications de transmission, les utilisateurs des appareils mobiles Apple et des téléphones Windows ne seront pas en mesure de détecter les événements, tels que les invitations aux messages instantanés ou les messages manqués, qui se produisent lorsque l’application mobile est désactivée.
    
    <div>
    

    > [!NOTE]  
    > Les clients mobiles Lync 2013 sur les appareils Apple ne requièrent aucune notification de transmission. Les clients mobiles Lync 2013 sur Windows Phone utilisent une notification de transmission. La planification de la notification de transmission et du centre de notifications de transmission de notifications reste inchangée pour les appareils mobiles Lync sur Windows Phone et Apple qui ne peuvent pas exécuter le client mobile Lync 2013.

    
    </div>

  - **Souhaitez-vous que tous les utilisateurs aient accès aux fonctionnalités de mobilité ou vous voulez peut-être spécifier les utilisateurs qui ont accès à ces fonctionnalités ?**
    
    Ce tableau décrit les fonctionnalités accessibles aux utilisateurs de Lync Server 2013. Les valeurs par défaut autorisent les appels via le bureau, autorisez la voix sur IP (VoIP) et activez la mobilité. Voici l’ensemble complet des options disponibles :
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Fonction/nom/paramètre de la fonction (les noms des paramètres de stratégie ne sont pas identiques)</th>
    <th>Description</th>
    <th>Introduis</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Activer la mobilité</p>
    <p>Nom du paramètre :<code>EnableMobility</code></p>
    <p>Étendue : Global/site/utilisateur</p></td>
    <td><p>Paramètre d’administration pour contrôler les utilisateurs au sein d’une étendue donnée sur laquelle Lync mobile n’est pas installé, si la stratégie est définie sur false, l’utilisateur ne peut pas se connecter au client.</p>
    <p>Le paramètre par défaut est true.</p></td>
    <td><p>Mise à jour cumulative pour Lync Server 2010:2011 novembre</p></td>
    </tr>
    <tr class="even">
    <td><p>Activer les appels vocaux extérieurs</p>
    <p>Nom du paramètre :<code>EnableOutsideVoice</code></p>
    <p>Étendue : Global/site/utilisateur</p></td>
    <td><p>Contrôle la capacité d’un utilisateur à utiliser appel via le bureau, une fonctionnalité qui permet aux utilisateurs de passer et de recevoir des appels en utilisant leur numéro de téléphone plutôt que leur numéro de téléphone mobile. Si elle est définie sur false, l’utilisateur ne pourra pas passer ou recevoir des appels en utilisant son numéro de téléphone sur son appareil mobile.</p>
    <p>Le paramètre par défaut est true.</p></td>
    <td><p>Mise à jour cumulative pour Lync Server 2010:2011 novembre</p></td>
    </tr>
    <tr class="odd">
    <td><p>Activer l’audio/la vidéo IP</p>
    <p>Nom du paramètre :<code>EnableIPAudioVideo</code></p>
    <p>Étendue : Global/site/utilisateur</p></td>
    <td><p>Contrôle si un utilisateur peut utiliser le protocole VoIP pour passer ou recevoir des appels vocaux ou vidéo sur son appareil mobile. Si elle est définie sur false, l’utilisateur n’est pas en mesure de passer ou de recevoir des appels VoIP ou vidéo sur son appareil.</p>
    <p>Le paramètre par défaut est true.</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    <tr class="even">
    <td><p>Exiger WiFi pour l’audio IP</p>
    <p>Nom du paramètre :<code>RequireWiFiForIPAudio</code></p>
    <p>Étendue : Global/site/utilisateur</p></td>
    <td><p>Ce paramètre détermine si le client est tenu d’émettre et de recevoir des appels sur le protocole VoIP sur réseau WiFi plutôt que sur le réseau de données cellulaires. S’il est défini sur true, l’utilisateur peut passer et recevoir des appels VoIP uniquement lorsqu’il est connecté à un réseau WiFi.</p>
    <p>Le paramètre par défaut est false.</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    <tr class="odd">
    <td><p>Exiger WiFi pour la vidéo IP</p>
    <p>Nom du paramètre :<code>RequireWiFiForIPVideo</code></p>
    <p>Étendue : Global/site/utilisateur</p></td>
    <td><p>Ce paramètre détermine si le client est tenu d’émettre et de recevoir des appels vidéo sur Wi-Fi plutôt que sur le réseau de données cellulaires. S’il est défini sur true, l’utilisateur peut passer et recevoir des appels vidéo uniquement lorsqu’il est connecté à un réseau Wi-Fi.</p>
    <p>Le paramètre par défaut est false.</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    </tbody>
    </table>
    
    Pour obtenir une description des paramètres de stratégie que vous pouvez configurer et sur la gestion des stratégies, voir [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy), [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy), [Get-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy), [Grant-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy) et [Remove-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy).

  - **Souhaitez-vous que les utilisateurs qui n’ont pas été activés pour voix entreprise puissent utiliser le Cliquer pour rejoindre des conférences ?**
    
    Pour que les utilisateurs puissent accéder aux fonctionnalités de mobilité et aux appels via le bureau, ils doivent être activés pour voix entreprise. Toutefois, les utilisateurs qui ne sont pas autorisés à utiliser la voix entreprise peuvent participer à des conférences en cliquant sur le lien sur leur appareil mobile, s’ils disposent d’une stratégie vocale appropriée. Vous pouvez affecter une stratégie vocale spécifique à ces utilisateurs ou vérifier qu’une stratégie globale ou une stratégie de niveau de site existe qui s’appliquent à ces utilisateurs. La stratégie vocale que vous attribuez doit avoir des enregistrements et des itinéraires d’utilisation de réseau téléphonique commuté (RTC) pour permettre aux utilisateurs de participer à une conférence. Pour plus d’informations sur la configuration de la stratégie vocale, des enregistrements d’utilisation RTC et des itinéraires, voir [Configuration des stratégies vocales, des enregistrements d’utilisation RTC et des itinéraires vocaux dans Lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md).
    
    <div>
    

    > [!NOTE]  
    > Les utilisateurs mobiles qui souhaitent utiliser l’option Cliquer pour rejoindre requièrent une stratégie vocale, ainsi que les enregistrements d’utilisation RTC et les itinéraires vocaux correspondants, car le fait de cliquer sur le lien sur l’appareil mobile génère un appel sortant de Lync Server 2013.

    
    </div>

<div>

## <a name="see-also"></a>Voir aussi


[Exigences techniques pour la mobilité dans Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md)  


[Configuration des stratégies vocales, des enregistrements d’utilisation RTC et des itinéraires vocaux dans Lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

