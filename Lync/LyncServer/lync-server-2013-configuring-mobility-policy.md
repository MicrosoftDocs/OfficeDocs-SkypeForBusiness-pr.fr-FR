---
title: 'Lync Server 2013 : Configuration de la stratégie de mobilité'
TOCTitle: Configuration de la stratégie de mobilité
ms:assetid: 595536e0-9bb3-49a3-8d13-1a77351ebc62
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Hh690018(v=OCS.15)
ms:contentKeyID: 49297262
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration de la stratégie de mobilité dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-02-13_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Lync Server 2013 fournit des stratégies de mobilité qui déterminent qui peut utiliser les fonctionnalités de mobilité, Appel via le bureau, VoIP ou la vidéo et si la fonctionnalité WiFi est requise pour la fonctionnalité VoIP ou la vidéo. La fonctionnalité Appel via le bureau permet à un utilisateur mobile d’effectuer et de recevoir des appels sur un téléphone mobile au moyen d’un numéro de téléphone professionnel au lieu du numéro de téléphone de l’appareil mobile. Elle empêche la personne appelée de voir le numéro de téléphone mobile de l’appelant et évite aux utilisateurs d’encourir des frais d’appel sortant. La configuration de la fonctionnalité VoIP et de la vidéo permet aux utilisateurs de recevoir et d’émettre des appels VoIP et des données vidéo. La configuration de la fonctionnalité VoIP et de la vidéo permet aux utilisateurs de recevoir et d’émettre des appels VoIP et des données vidéo. Les paramètres de l’utilisation de la fonctionnalité WiFi déterminent si l’appareil d’un utilisateur doit utiliser un réseau WiFi de préférence à un réseau cellulaire de données.

Par défaut, les fonctionnalités de mobilité, d’Appel via le bureau, VoIP et vidéo sont activées. Les paramètres permettant d’exiger la fonctionnalité WiFi pour les fonctionnalités VoIP et vidéo sont désactivés. Les administrateurs peuvent déterminer qui a accès à ces fonctionnalités en exécutant une applet de commande. Il est possible de désactiver les options globalement, par site ou par utilisateur.

Pour pouvoir utiliser les fonctionnalités de mobilité et d’Appel via le bureau, les utilisateurs doivent remplir les conditions préalables suivantes :

  - les utilisateurs doivent être activés pour Lync Server 2013 ;

  - les utilisateurs doivent être activés pour Voix Entreprise ;

  - une stratégie de mobilité dont l’option **EnableMobility** a la valeur True doit être affectée aux utilisateurs.

Pour pouvoir utiliser la fonctionnalité d’Appel via le bureau, les utilisateurs doivent remplir les deux conditions supplémentaires suivantes :

  - une stratégie de voix ayant l’option **Activer la sonnerie simultanée de téléphones** activée doit être affectée aux utilisateurs ;

  - une stratégie de mobilité dont l’option **EnableOutsideVoice** a la valeur True doit être affectée aux utilisateurs.

> [!NOTE]  
> Les utilisateurs qui ne sont pas activés pour Voix Entreprise peuvent utiliser leur appareil mobile pour effectuer des appels VoIP depuis Lync vers Lync ou rejoindre des conférences par le biais du lien Cliquez pour rejoindre affiché sur leur appareil mobile, si vous affectez à ces utilisateurs les options appropriées pour une stratégie de voix. Pour plus d’informations, reportez-vous à <a href="lync-server-2013-defining-your-mobility-requirements.md">Définition de la configuration requise pour la mobilité pour Lync Server 2013</a>.

Pour plus d’informations sur l’activation des utilisateurs pour Lync Server 2013, reportez-vous à [Désactivation ou réactivation d’un compte d’utilisateur pour Lync Server](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md). Pour plus d’informations sur l’activation des utilisateurs pour Voix Entreprise, reportez-vous à [Activation des utilisateurs pour Voix Entreprise dans Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md). Pour plus d’informations sur la définition des options de stratégie de voix, reportez-vous à [Modifier une stratégie de voix et configurer des enregistrements d’utilisation PSTN dans Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md).

## Pour modifier la stratégie de mobilité globale

1.  Ouvrez une session en tant que membre du rôle CsAdministrator sur un ordinateur sur lequel Lync Server Management Shell et Ocscore sont installés.

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Désactivez globalement l’accès à la mobilité et l’Appel via le bureau.
    
        Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
    
    > [!NOTE]  
    > Vous pouvez désactiver l’Appel via le bureau sans désactiver l’accès à la mobilité. En revanche, il est impossible de désactiver la mobilité sans également désactiver l’Appel via le bureau.

## Pour modifier la stratégie de mobilité par site

1.  Ouvrez une session en tant que membre du rôle CsAdministrator sur un ordinateur sur lequel Lync Server Management Shell et Ocscore sont installés.

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Créez une stratégie au niveau du site, désactivez les fonctionnalités VoIP et vidéo et activez l’exigence de la fonctionnalité WiFi pour les fonctions IP audio et IP vidéo par site. Dans la ligne de commande, tapez :
    
        New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $False -RequireWiFiForIPAudio $True -RequireWiFiForIPVideo $True

## Pour modifier la stratégie de mobilité par utilisateur

1.  Ouvrez une session en tant que membre du rôle CsAdministrator sur un ordinateur sur lequel Lync Server Management Shell et Ocscore sont installés.

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Créez des stratégies de mobilité au niveau de l’utilisateur et désactivez la mobilité et l’Appel via le bureau par utilisateur. Dans la ligne de commande, tapez :
    
        New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
    
    Vous pouvez désactiver l’Appel via le bureau sans désactiver l’accès à la mobilité. En revanche, il est impossible de désactiver la mobilité sans également désactiver l’Appel via le bureau.
    
    Exemple :
    
        New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity -MobileUser1@contoso.com -PolicyName Tag:disableOutsideVoice

## Voir aussi

#### Tâches

[Désactivation ou réactivation d’un compte d’utilisateur pour Lync Server](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  
[Activation des utilisateurs pour Voix Entreprise dans Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md)  
[Modifier une stratégie de voix et configurer des enregistrements d’utilisation PSTN dans Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  

#### Concepts

[Définition de la configuration requise pour la mobilité pour Lync Server 2013](lync-server-2013-defining-your-mobility-requirements.md)  

#### Autres ressources

[New-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsMobilityPolicy)  
[Set-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsMobilityPolicy)  
[Get-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsMobilityPolicy)  
[Grant-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsMobilityPolicy)  
[Remove-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsMobilityPolicy)

