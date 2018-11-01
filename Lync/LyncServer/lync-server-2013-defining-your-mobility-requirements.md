---
title: 'Lync Server 2013 : Définition de la configuration requise pour la mobilité'
TOCTitle: Définition de la configuration requise pour la mobilité
ms:assetid: b7608335-cdeb-4aae-8e4b-d80c55f0d62b
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Hh690039(v=OCS.15)
ms:contentKeyID: 49298616
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Définition de la configuration requise pour la mobilité pour Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Durant la phase de planification de la fonctionnalité de mobilité de Lync Server 2013, lorsque vous utilisez des clients Lync 2010 Mobile et Lync 2013 Mobile, vous prenez certaines décisions qui déterminent les étapes de déploiement nécessaires.

Voici les questions auxquelles vous devez répondre :

  - **Souhaitez-vous utiliser la découverte automatique des clients mobiles Lync ?**
    
    Si vous souhaitez prendre en charge la découverte automatique, vous devez créer de nouveaux enregistrements DNS (Domain Name System) internes et externes, ajouter d’autres noms du sujet aux certificats sur les serveurs frontaux, les directeurs et le proxy inverse, et modifier les règles de publication web existantes sur le proxy inverse. Pour plus d’informations, reportez-vous à [Exigences techniques pour la mobilité dans Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md). Avec la découverte automatique, les utilisateurs peuvent trouver automatiquement les services web Lync Server 2013 depuis n’importe quel emplacement (sur le réseau d’entreprise ou en dehors) sans avoir à entrer d’URL dans les paramètres de leur appareil mobile.
    
    Si vous utilisez des paramètres manuels plutôt que la découverte automatique, les utilisateurs mobiles doivent entrer manuellement les URL suivantes dans leur appareil mobile :
    
      - https://\<nom\_domaine\_complet\_pool\_ext\>/Autodiscover/autodiscoverservice.svc/Root pour l’accès externe
    
      - https://\<nom\_domaine\_complet\_pool\_int\>/AutoDiscover/autodiscoverservice.svc/Racine pour l’accès interne
    
    Nous vous conseillons vivement d’utiliser la découverte automatique. Les paramètres manuels s’utilisent principalement à des fins d’identification et de résolution des problèmes.

  - **Si vous décidez de prendre en charge la découverte automatique, souhaitez-vous mettre à jour les certificats sur le proxy inverse avec d’autres noms de sujet pour chaque domaine IP ?**
    
    Si vous avez de nombreux domaines IP, la mise à jour des certificats publics sur le proxy inverse peut être très coûteuse. Dans ce cas, vous pouvez choisir de mettre en œuvre la découverte automatique de telle sorte que la demande initiale du service de découverte automatique utilise le protocole HTTP sur le port 80, au lieu d’utiliser le protocole HTTPS sur le port 443. Cependant, cette approche n’est pas recommandée. Si vous décidez de choisir cette alternative, vous n’êtes pas obligé de mettre à jour les certificats sur le proxy inverse mais vous devez créer une règle de publication web pour le protocole HTTP sur le port 80. Pour plus d’informations, reportez-vous à [Exigences techniques pour la mobilité dans Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).

  - **Souhaitez-vous prendre en charge les clients mobiles Lync internes et externes au réseau d’entreprise, ou uniquement ceux internes au réseau d’entreprise ?**
    
    Lorsque vous prenez en charge les clients mobiles internes et externes à votre réseau, les appareils mobiles peuvent accéder aux fonctionnalités de mobilité depuis n’importe quel emplacement. La configuration par défaut consiste à prendre en charge les clients internes et externes au réseau d’entreprise.
    
    Même si la configuration par défaut permet au trafic des clients mobiles de traverser le site externe, vous pouvez limiter ce trafic au réseau d’entreprise interne. Dans ce cas, les utilisateurs peuvent utiliser les applications mobiles Lync sur leur appareil mobile uniquement lorsqu’ils se trouvent sur le réseau.
    
    Pour les déploiements qui prennent en charge la mobilité à l’aide du service de mobilité Mcx et de Lync 2010 Mobile, vous devez exécuter l’applet de commande **Set-CsMcxConfiguration**. Pour définir la mobilité uniquement pour un usage interne, vous devez exécuter une commande semblable à la suivante :
    
        Set-CsMcxConfiguration -Identity site:Redmond -ExposedWebURL Internal
    
    > [!NOTE]  
    > Aucune configuration supplémentaire n’est requise pour UCWA. UCWA n’offre aucune configuration interne-uniquement équivalente.    
    > [!IMPORTANT]  
    > Si vous utilisez un serveur frontal ou des pools de serveurs frontauxLync Server 2013 et que <strong>vous n’avez pas</strong> de serveurs frontaux ou de pools de serveurs frontauxLync Server 2010, <strong>il n’y a pas d’exigences concernant la persistance basée sur les cookies</strong>. Si vous devez conserver des serveurs frontaux ou pools de serveurs frontauxLync Server 2010, les mêmes règles que dans Lync Server 2010 s’appliquent concernant la persistance basée sur les cookies.

  - **Souhaitez-vous prendre en charge les notifications push pour les appareils Apple iOS et Windows Phone ?**
    
    Si vous prenez en charge les notifications push, les appareils Apple iOS et Windows Phones reçoivent une notification des événements qui se produisent pendant que l’application mobile est inactive. Vous devez configurer votre serveur Edge de sorte qu’il entretienne une relation de fédération avec le service de notification push de Lync Server, qui se trouve dans le centre de données Lync Online, et exécuter une applet de commande afin d’activer les notifications push.
    
    Si vous souhaitez prendre en charge les notifications push sur votre réseau Wi-Fi, en plus de la prise en charge des notifications push sur les réseaux de données ou 3G de vos fournisseurs d’appareils mobiles, vous devez ouvrir le port 5223 sortant sur votre réseau Wi-Fi d’entreprise. La prise en charge les notifications push sur le réseau Wi-Fi permet de prendre en charge les appareils mobiles qui utilisent uniquement le réseau Wi-Fi et ceux bénéficiant d’une mauvaise réception à l’intérieur.
    
    > [!IMPORTANT]  
    > L’ouverture du port TCP 5223 est nécessaire uniquement lors de la prise en charge d’appareils Apple exécutant le client Lync 2010 Mobile.    
    Si vous ne prenez pas en charge les notifications push, les utilisateurs d’appareils mobiles Apple et Windows Phone ne seront pas tenus au courant des événements (tels que les invitations de messagerie instantanée ou les messages manqués) qui se produisent lorsque l’application mobile est inactive.
    
    > [!NOTE]  
    > Les notifications push ne sont pas nécessaires sur les clients Lync 2013 Mobile sur appareils Apple. Les clients Lync 2013 Mobile sur Windows Phone utilisent les notifications push. La planification des notifications push et du centre d’échanges de notifications push demeure identique pour Lync Mobile sur Windows Phone et les appareils Apple qui ne peuvent pas exécuter le client Lync 2013 Mobile.

  - **Souhaitez-vous que tous les utilisateurs aient accès aux fonctionnalités de mobilité ou voulez-vous être en mesure de spécifier les utilisateurs qui ont accès à ces fonctionnalités ?**
    
    Le tableau décrit les fonctionnalités accessibles aux utilisateurs dans Lync Server 2013. Les paramètres par défaut autorisent l’Appel via le bureau et la Voix sur IP (VoIP) et activent la mobilité. Voici l’ensemble complet d’options disponibles :
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Fonctionnalité/Nom du paramètre/Étendue (Les noms des paramètres de stratégie peuvent différer)</th>
    <th>Description</th>
    <th>Introduction</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Activer la mobilité</p>
    <p>Nom du paramètre : <code>EnableMobility</code></p>
    <p>Étendue : Globale/Site/Utilisateur</p></td>
    <td><p>Paramètre d’administration permettant de contrôler les utilisateurs dans une étendue donnée qui disposent de Lync Mobile. Si la stratégie a la valeur False, l’utilisateur ne peut pas se connecter au client.</p>
    <p>La valeur par défaut est True.</p></td>
    <td><p>Mise à jour cumulative pour Lync Server 2010 de novembre 2011</p></td>
    </tr>
    <tr class="even">
    <td><p>Activer la voix extérieure</p>
    <p>Nom du paramètre : <code>EnableOutsideVoice</code></p>
    <p>Étendue : Globale/Site/Utilisateur</p></td>
    <td><p>Contrôle la capacité d’un utilisateur à utiliser l’Appel via le bureau, une fonctionnalité qui lui permet d’effectuer et de recevoir des appels à l’aide de son numéro professionnel au lieu de son numéro de téléphone mobile. Si ce paramètre a la valeur False, l’utilisateur ne pourra pas effectuer ou recevoir d’appel à l’aide de son numéro professionnel depuis son numéro de téléphone mobile.</p>
    <p>La valeur par défaut est True.</p></td>
    <td><p>Mise à jour cumulative pour Lync Server 2010 de novembre 2011</p></td>
    </tr>
    <tr class="odd">
    <td><p>Activer l’audio/la vidéo IP</p>
    <p>Nom du paramètre : <code>EnableIPAudioVideo</code></p>
    <p>Étendue : Globale/Site/Utilisateur</p></td>
    <td><p>Ce paramètre détermine si un utilisateur peut utiliser VoIP pour effectuer ou recevoir des appels sur son appareil mobile. S’il a la valeur False, l’utilisateur ne pourra pas effectuer ou recevoir d’appel vidéo ou VoIP sur son appareil mobile.</p>
    <p>La valeur par défaut est True.</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    <tr class="even">
    <td><p>Exiger WiFi pour l’audio IP</p>
    <p>Nom du paramètre : <code>RequireWiFiForIPAudio</code></p>
    <p>Étendue : Globale/Site/Utilisateur</p></td>
    <td><p>Ce paramètre détermine si le client devra effectuer et recevoir les appels sur VoIP sur WiFi plutôt que sur le réseau de données cellulaire. S’il a la valeur True, l’utilisateur peut effectuer et recevoir des appels VoIP uniquement lorsqu’il est connecté à un réseau WiFi.</p>
    <p>La valeur par défaut est False.</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    <tr class="odd">
    <td><p>Exiger WiFi pour la vidéo IP</p>
    <p>Nom du paramètre : <code>RequireWiFiForIPVideo</code></p>
    <p>Étendue : Globale/Site/Utilisateur</p></td>
    <td><p>Ce paramètre détermine si le client devra effectuer et recevoir les appels vidéo sur WiFi plutôt que sur le réseau de données cellulaire. S’il a la valeur True, l’utilisateur peut effectuer et recevoir des appels vidéo uniquement lorsqu’il est connecté à un réseau WiFi.</p>
    <p>La valeur par défaut est False.</p></td>
    <td><p>Microsoft Lync Server 2013</p></td>
    </tr>
    </tbody>
    </table>
    
    Pour obtenir une description des paramètres de stratégie configurables et pour plus d’informations sur la façon de gérer les stratégies, reportez-vous à [New-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsMobilityPolicy), [Set-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsMobilityPolicy), [Get-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsMobilityPolicy), [Grant-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsMobilityPolicy) et [Remove-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsMobilityPolicy).

  - **Souhaitez-vous que les utilisateurs qui ne sont pas activés pour Voix Entreprise puissent utiliser la fonctionnalité Cliquez pour participer afin de rejoindre des conférences ?**
    
    Pour que les utilisateurs puissent accéder aux fonctionnalités de mobilité et à Appel via le bureau, ils doivent être activés pour Voix Entreprise. Cependant, les utilisateurs qui ne sont pas activés pour Voix Entreprise peuvent participer à des conférences en cliquant sur le lien sur leur appareil mobile si une stratégie de voix appropriée leur a été affectée. Vous pouvez affecter une stratégie de voix spécifique à ces utilisateurs ou vous assurer qu’il existe une stratégie globale ou au niveau du site qui s’applique à eux. La stratégie de voix que vous affectez doit avoir des enregistrements d’utilisation RTC (réseau téléphonique commuté) et des itinéraires qui définissent les zones vers lesquelles les utilisateurs peuvent téléphoner pour rejoindre une conférence. Pour plus d’informations sur la définition d’une stratégie de voix, sur les enregistrements d’utilisation RTC et sur les itinéraires, reportez-vous à [Configuration des stratégies de voix, des enregistrements d’utilisation du RTC et des itinéraires des communications vocales dans Lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md).
    
    > [!NOTE]  
    > Les utilisateurs mobiles qui souhaitent utiliser Cliquez pour participer requièrent une stratégie de voix, ainsi que les enregistrements d’utilisation RTC et itinéraires des communications vocales associés, car un clic sur le lien sur l’appareil mobile entraîne l’établissement d’un appel sortant à partir de Lync Server 2013.

## Voir aussi

#### Concepts

[Exigences techniques pour la mobilité dans Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md)  

#### Autres ressources

[Configuration des stratégies de voix, des enregistrements d’utilisation du RTC et des itinéraires des communications vocales dans Lync Server 2013](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)

