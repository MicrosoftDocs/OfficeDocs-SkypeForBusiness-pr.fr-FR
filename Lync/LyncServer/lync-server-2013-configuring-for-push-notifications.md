---
title: 'Lync Server 2013 : Configuration des notifications push'
TOCTitle: Configuration des notifications push
ms:assetid: d77f2c06-0fe6-45d5-8f08-808ab871b3e0
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Hh690047(v=OCS.15)
ms:contentKeyID: 49298999
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration des notifications push dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-02-12_

Des notifications push, sous forme de badges, icônes ou alertes, peuvent être envoyées à un appareil mobile même lorsque l’application mobile est inactive. Ces notifications signalent à un utilisateur qu’un événement s’est produit, par exemple, une invitation de messagerie instantanée nouvelle ou manquée ou un message vocal. Le service de mobilité de Lync Server 2013 envoie les notifications au service de notification Lync Server basé dans le nuage, qui envoie ensuite les notifications au service de notification Push d’Apple (APNS) (pour un appareil Apple exécutant le client Lync 2010 Mobile) ou au système de notification de transmission de Microsoft (MPNS) (pour un appareil Windows Phone exécutant le client Lync 2010 Mobile ou Lync 2013 Mobile).

> [!IMPORTANT]  
> Si vous utilisez Windows Phone avec le client Lync 2010 Mobile ou Lync 2013 Mobile, les notifications push revêtent une haute importance.<br />
Si vous utilisez Lync 2010 Mobile sur des appareils Apple, les notifications push revêtent une haute importance.<br />
Si vous utilisez Lync 2013 Mobile sur des appareils Apple, les notifications push ne sont plus nécessaires.

Vous pouvez configurer votre topologie de sorte qu’elle prenne en charge les notifications push en procédant comme suit :

  - Si votre environnement comporte un serveur EdgeLync Server 2010 ou Lync Server 2013, vous devez ajouter un nouveau fournisseur d’hébergement, Microsoft Lync Online, puis configurer la fédération de fournisseurs d’hébergement entre votre organisation et Lync Online.

  - Si votre environnement comporte un serveur EdgeOffice Communications Server 2007 R2, vous devez configurer la fédération SIP directe avec push.lync.com.
    
    > [!NOTE]  
    > Push.lync.com est un domaine Microsoft Office 365 pour le service de notifications push.

  - Pour activer les notifications push, vous devez exécuter l’applet de commande **Set-CsPushNotificationConfiguration**. Par défaut, les notifications push sont désactivées.

  - Testez la configuration de fédération et les notifications push.

## Pour configurer les notifications push avec un serveur EdgeLync Server 2013 ou Lync Server 2010

1.  Ouvrez une session en tant que membre du groupe RtcUniversalServerAdmins sur un ordinateur sur lequel Lync Server Management Shell et Ocscore sont installés.

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Ajoutez un fournisseur d’hébergement en ligne Lync Server. Dans la ligne de commande, tapez :
    
        New-CsHostingProvider -Identity <unique identifier for Lync Online hosting provider> -Enabled $True -ProxyFqdn <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
    
    Exemple :
    
        New-CsHostingProvider -Identity "LyncOnline" -Enabled $True -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
    
    > [!NOTE]  
    > Vous ne pouvez pas avoir plus d’une relation de fédération avec un même fournisseur d’hébergement. Autrement dit, si vous avez déjà configuré un fournisseur d’hébergement ayant une relation de fédération avec sipfed.online.lync.com, vous ne devez pas ajouter d’autre fournisseur d’hébergement, même si l’identité du fournisseur d’hébergement est différente de LyncOnline.

4.  Configurez la fédération de fournisseurs d’hébergement entre votre organisation et le service de notifications push de Lync Online. Dans la ligne de commande, tapez :
    
        New-CsAllowedDomain -Identity "push.lync.com"

## Pour configurer les notifications push avec un serveur EdgeOffice Communications Server 2007 R2

1.  Ouvrez une session sur le serveur Edge en tant que membre du groupe RtcUniversalServerAdmins.

2.  Cliquez sur **Démarrer** , sur **Tous les programmes** , sur **Outils d’administration** , puis sur **Gestion de l’ordinateur** .

3.  Dans l’arborescence de la console, développez **Services et applications** , cliquez avec le bouton droit sur **Microsoft Office Communications Server 2007 R2** , puis cliquez sur **Propriétés** .

4.  Sous l’onglet **Autoriser** , cliquez sur **Ajouter** .

5.  Dans la boîte de dialogue **Ajouter un partenaire fédéré** , procédez comme suit :
    
      - Dans **Nom de domaine du partenaire fédéré** , tapez **push.lync.com** .
    
      - Dans **Serveur Edge d’accès du partenaire fédéré** , tapez **sipfed.online.lync.com**.
    
      - Cliquez sur **OK** .

## Pour activer les notifications push

1.  Ouvrez une session en tant que membre du rôle CsAdministrator sur un ordinateur sur lequel Lync Server Management Shell et Ocscore sont installés.

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Activez les notifications push. Dans la ligne de commande, tapez :
    
        Set-CsPushNotificationConfiguration -EnableApplePushNotificationService $True -EnableMicrosoftPushNotificationService $True

4.  Activez la fédération. Dans la ligne de commande, tapez :
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

## Pour tester la fédération et les notifications push

1.  Ouvrez une session en tant que membre du rôle CsAdministrator sur un ordinateur sur lequel Lync Server Management Shell et Ocscore sont installés.

2.  Démarrez Lync Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Testez la configuration de la fédération. Dans la ligne de commande, tapez :
    
        Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
    
    Exemple :
    
        Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com

4.  Testez les notifications push. Dans la ligne de commande, tapez :
    
        Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
    
    Exemple :
    
        Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com

## Voir aussi

#### Autres ressources

[Test-CsFederatedPartner](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsFederatedPartner)  
[Test-CsMcxPushNotification](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsMcxPushNotification)

