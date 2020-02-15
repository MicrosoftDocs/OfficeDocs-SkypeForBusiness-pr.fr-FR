---
title: 'Lync Server 2013 : définition de vos besoins en matière de mobilité'
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
ms.openlocfilehash: d0eeb3feda41a62472c79214681bc4b9ce0a22ee
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029635"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-mobility-requirements-for-lync-server-2013"></a>Définition de la configuration requise pour la mobilité pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-14_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Lors de la phase de planification de la fonctionnalité de mobilité Lync Server 2013, lorsque vous utilisez les clients mobiles Lync 2010 mobile et Lync 2013, vous prenez des décisions qui déterminent vos étapes de déploiement.

Voici les décisions que vous devez prendre en compte :

  - **Souhaitez-vous utiliser la découverte automatique des clients mobiles Lync ?**
    
    Si vous souhaitez prendre en charge la découverte automatique, vous devez créer des enregistrements DNS (Domain Name System) internes et externes, ajouter d’autres noms de sujet aux certificats sur les serveurs frontaux, les directeurs et le proxy inverse, et modifier les règles de publication existantes. sur le proxy inverse. Pour plus d’informations, voir [Technical Requirements for Mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md). La découverte automatique permet aux utilisateurs de localiser automatiquement les services Web Lync Server 2013 depuis n’importe quel emplacement à l’intérieur ou à l’extérieur du réseau d’entreprise, sans avoir à entrer des URL dans leurs paramètres d’appareil mobile.
    
    Si vous utilisez des paramètres manuels au lieu de la découverte automatique, les utilisateurs mobiles doivent entrer manuellement les URL suivantes dans leurs appareils mobiles :
    
      - https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/root pour l’accès externe
    
      - https://\<IntPoolFQDN\>/Autodiscover/Autodiscoverservice. svc/root pour l’accès interne
    
    Nous vous conseillons vivement d’utiliser la découverte automatique. Les paramètres manuels s’utilisent principalement à des fins de dépannage.

  - **Si vous décidez de prendre en charge la découverte automatique, souhaitez-vous mettre à jour les certificats sur le proxy inverse avec d’autres noms de sujet pour chaque domaine IP ?**
    
    Si vous avez de nombreux domaines IP, la mise à jour des certificats publics sur le proxy inverse peut être très coûteuse. Dans ce cas, vous pouvez choisir d’implémenter la découverte automatique de sorte que la demande de service de découverte automatique initiale utilise le protocole HTTP sur le port 80, au lieu d’utiliser le protocole HTTPs sur le port 443. Toutefois, il ne s’agit pas de l’approche recommandée. Si vous décidez de choisir cette alternative, vous n’avez pas besoin de mettre à jour les certificats sur le proxy inverse, mais vous devez créer une règle de publication Web pour HTTP sur le port 80. Pour plus d’informations, reportez-vous à [configuration technique requise pour la mobilité dans Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).

  - **Souhaitez-vous prendre en charge les clients mobiles Lync internes et externes au réseau d’entreprise, ou uniquement ceux internes au réseau d’entreprise ?**
    
    Lorsque vous prenez en charge les clients mobiles internes et externes à votre réseau, les appareils mobiles peuvent accéder aux fonctionnalités de mobilité depuis n’importe quel emplacement. La configuration par défaut consiste à prendre en charge les clients internes et externes au réseau d’entreprise.
    
    Bien que la configuration par défaut permette au trafic des clients mobiles de traverser le site externe, vous pouvez limiter ce trafic au réseau d’entreprise interne. Dans ce cas, les utilisateurs peuvent utiliser les applications mobiles Lync sur leur appareil mobile uniquement lorsqu’ils se trouvent sur le réseau.
    
    Pour les déploiements qui prennent en charge la mobilité à l’aide du service de mobilité MCX et de Lync 2010 mobile, vous exécutez l’applet **de commande Set-CsMcxConfiguration** . Pour définir la mobilité pour un usage interne uniquement, vous devez utiliser une commande similaire à celle-ci :
    
        Set-CsMcxConfiguration -Identity site:Redmond -ExposedWebURL Internal
    
    <div>
    

    > [!NOTE]  
    > Aucune configuration supplémentaire n’est requise pour UCWA. UCWA n’a pas de configuration équivalente uniquement en interne.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > Si vous utilisez un serveur frontal ou des&nbsp;pools frontaux lync Server 2013 et <STRONG>que vous ne disposez pas</STRONG> de serveurs frontaux ou de pools frontaux Lync Server 2010&nbsp;, il n' <STRONG>est pas nécessaire d’utiliser la persistance basée sur les cookies</STRONG>. Si vous avez besoin de conserver les serveurs frontaux ou les pools frontaux Lync Server 2010&nbsp;, les mêmes règles s’appliquent toujours comme dans lync Server 2010 pour la persistance basée sur les cookies.

    
    </div>

  - **Souhaitez-vous prendre en charge les notifications push pour les appareils Apple iOS et Windows Phone ?**
    
    Si vous prenez en charge les notifications push, les appareils Apple iOS et Windows Phones reçoivent une notification des événements qui se produisent pendant que l’application mobile est inactive. Vous devez configurer votre serveur Edge de sorte qu’il dispose d’une relation de Fédération avec le service de notifications d’envoi sur le Cloud de Lync Server, qui se trouve dans le centre de contenu Lync Online et exécute une applet de commande pour activer les notifications de transmission.
    
    Si vous souhaitez prendre en charge les notifications de type transmission via votre réseau Wi-Fi, en plus de prendre en charge les notifications de type transmission sur les réseaux de données ou 3G des fournisseurs d’appareils mobiles, vous devez ouvrir le port 5223 sortant sur votre réseau Wi-Fi d’entreprise. Le fait de prendre en charge les notifications push sur le réseau Wi-Fi permet de prendre en charge les appareils mobiles qui utilisent uniquement le réseau Wi-Fi et ceux bénéficiant d’une mauvaise réception à l’intérieur.
    
    <div>
    

    > [!IMPORTANT]  
    > L’ouverture du port TCP 5223 est requise uniquement lors de la prise en charge des appareils Apple exécutant le client mobile Lync 2010.

    
    </div>
    
    Si vous ne prenez pas en charge les notifications de type diffuser, les utilisateurs des appareils mobiles Apple et des téléphones Windows ne pourront pas découvrir les événements, tels que les invitations de messagerie instantanée ou les messages manqués, qui se produisent lorsque l’application mobile est inactive.
    
    <div>
    

    > [!NOTE]  
    > Les clients mobiles Lync 2013 sur les appareils Apple ne nécessitent pas de notification de transmission. Les clients mobiles Lync 2013 sur Windows Phone utilisent la notification de transmission. La planification de la notification de transmission et le centre de notifications poussés restent identiques pour Lync mobile sur Windows Phone et les appareils Apple qui ne peuvent pas exécuter le client mobile Lync 2013.

    
    </div>

  - **Voulez-vous que tous les utilisateurs aient accès aux fonctionnalités de mobilité ou voulez-vous être en mesure de spécifier les utilisateurs qui ont accès à ces fonctionnalités ?**
    
    Le tableau décrit les fonctionnalités disponibles pour les utilisateurs dans Lync Server 2013. Les paramètres par défaut autorisent les appels via le bureau, la voix sur IP (VoIP) et l’activation de la mobilité. Voici l’ensemble complet des options disponibles :
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Nom/étendue de la fonctionnalité/paramètre (les noms de paramètres de stratégie ne peuvent pas être identiques)</th>
    <th>Description</th>
    <th>Introduit</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Activer la mobilité</p>
    <p>Nom du paramètre :<code>EnableMobility</code></p>
    <p>Étendue : Global/site/User</p></td>
    <td><p>Paramètres d’administration pour contrôler les utilisateurs d’une étendue donnée sur laquelle Lync mobile est installé, si la stratégie est définie sur false, l’utilisateur ne peut pas se connecter au client.</p>
    <p>Le paramètre par défaut est True.</p></td>
    <td><p>Mise à jour cumulative pour Lync Server 2010 : novembre 2011</p></td>
    </tr>
    <tr class="even">
    <td><p>Activer la voix en extérieur</p>
    <p>Nom du paramètre :<code>EnableOutsideVoice</code></p>
    <p>Étendue : Global/site/User</p></td>
    <td><p>Contrôle la capacité d’un utilisateur à utiliser l’appel via le bureau, une fonctionnalité qui permet aux utilisateurs de passer et de recevoir des appels à l’aide de leur numéro professionnel au lieu de leur numéro de téléphone mobile. Si la valeur est définie sur false, l’utilisateur ne peut pas passer ou recevoir des appels à l’aide de son numéro de travail à partir de son appareil mobile.</p>
    <p>Le paramètre par défaut est true.</p></td>
    <td><p>Mise à jour cumulative pour Lync Server 2010 : novembre 2011</p></td>
    </tr>
    <tr class="odd">
    <td><p>Activer l’audio et la vidéo IP</p>
    <p>Nom du paramètre :<code>EnableIPAudioVideo</code></p>
    <p>Étendue : Global/site/User</p></td>
    <td><p>Contrôle si un utilisateur peut utiliser VoIP pour passer ou recevoir des appels vocaux ou vidéo sur son appareil mobile. Si la valeur est définie sur false, l’utilisateur ne sera pas en mesure d’effectuer ou de recevoir des appels VoIP ou vidéo sur son appareil.</p>
    <p>Le paramètre par défaut est True.</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    <tr class="even">
    <td><p>Exiger WiFi pour l’audio IP</p>
    <p>Nom du paramètre :<code>RequireWiFiForIPAudio</code></p>
    <p>Étendue : Global/site/User</p></td>
    <td><p>Ce paramètre définit si le client devra passer et recevoir des appels via VoIP sur WiFi au lieu du réseau de données cellulaires. Si la valeur est définie sur true, l’utilisateur peut passer et recevoir des appels VoIP uniquement lorsqu’il est connecté à un réseau WiFi.</p>
    <p>Le paramètre par défaut est False.</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    <tr class="odd">
    <td><p>Exiger WiFi pour la vidéo IP</p>
    <p>Nom du paramètre :<code>RequireWiFiForIPVideo</code></p>
    <p>Étendue : Global/site/User</p></td>
    <td><p>Ce paramètre définit si le client devra passer et recevoir des appels vidéo sur Wi-Fi plutôt que sur le réseau de données cellulaires. Si la valeur est définie sur true, l’utilisateur peut passer et recevoir des appels vidéo uniquement lorsqu’il est connecté à un réseau Wi-Fi.</p>
    <p>Le paramètre par défaut est False.</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    </tbody>
    </table>
    
    Pour obtenir une description des paramètres de stratégie que vous pouvez configurer et gérer les stratégies, consultez les rubrique [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy), [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy), [Get-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy), [Grant-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy) et [Remove-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy).

  - **Souhaitez-vous que les utilisateurs qui ne sont pas activés pour Voix Entreprise puissent utiliser la fonctionnalité Cliquez pour participer afin de rejoindre des conférences ?**
    
    Pour que les utilisateurs puissent accéder aux fonctionnalités de mobilité et à Appel via le bureau, ils doivent être activés pour Voix Entreprise. Toutefois, les utilisateurs qui ne sont pas activés pour voix entreprise peuvent participer à des conférences en cliquant sur le lien sur leur appareil mobile, s’ils disposent d’une stratégie de voix appropriée. Vous pouvez affecter une stratégie de voix spécifique à ces utilisateurs ou vous assurer qu’il existe une stratégie globale ou une stratégie au niveau du site qui s’applique à ces utilisateurs. La stratégie de voix que vous affectez doit avoir des itinéraires et des itinéraires d’utilisation du réseau téléphonique commuté (PSTN) qui définissent les domaines dans lesquels les utilisateurs peuvent participer à une conférence. Pour plus d’informations sur la stratégie de voix, les enregistrements d’utilisation RTC et les itinéraires, voir [Configuration des stratégies de voix, des enregistrements d’utilisation PSTN et des itinéraires des communications vocales dans Lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md).
    
    <div>
    

    > [!NOTE]  
    > Les utilisateurs mobiles qui souhaitent utiliser l’option Cliquer pour rejoindre nécessitent une stratégie de voix, ainsi que les enregistrements d’utilisation RTC et les itinéraires vocaux associés, car le fait de cliquer sur le lien sur l’appareil mobile entraîne un appel sortant de Lync Server 2013.

    
    </div>

<div>

## <a name="see-also"></a>Voir aussi


[Configuration technique requise pour la mobilité dans Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md)  


[Configuration des stratégies de voix, des enregistrements d’utilisation RTC et des itinéraires des communications vocales dans Lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

