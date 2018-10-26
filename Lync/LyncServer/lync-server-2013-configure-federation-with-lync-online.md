---
title: 'Lync Server 2013 : Configuration de la fédération avec Lync Online'
TOCTitle: Configuration de la fédération avec Lync Online
ms:assetid: a10bd1d5-c003-46db-9f57-7d55d3fa08da
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205126(v=OCS.15)
ms:contentKeyID: 49298357
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration de la fédération de Lync Server 2013 avec Lync Online

 

_**Dernière rubrique modifiée :** 2016-12-08_

Pour configurer l’interopérabilité entre votre déploiement local et Skype Entreprise Online, suivez la procédure de cette section.

## Configurez votre service Edge local pour la fédération avec Skype Entreprise Online

La fédération permet aux utilisateurs dans votre déploiement local de communiquer avec les utilisateurs d’Office 365 dans votre organisation. Pour configurer la fédération, exécutez l’applet de commande suivante :

```
Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting
```
```
New-CSHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
```

## Configurez votre locataire Skype Entreprise Online pour un espace d’adressage SIP partagé

Une adresse SIP (Session Initiation Protocol) de l’utilisateur est un identificateur unique pour chaque utilisateur d’un réseau, elle est semblable à un numéro de téléphone ou une adresse de messagerie. Avant d’essayer de déplacer un utilisateur Lync hébergé en local dans Skype Entreprise Online, vous devez configurer votre client Office 365 de façon à utiliser un espace d’adressage SIP (Session Initiation Protocol) partagé avec votre déploiement local. À défaut de cette configuration, vous pouvez obtenir le message d’erreur suivant :

Move-CsUser : HostedMigration fault: Error=(510), Description=(Le client de cet utilisateur n’est pas configuré pour l’espace d’adressage SIP partagé.)

Pour configurer un espace d’adressage SIP partagé, établissez une session PowerShell distante avec Skype Entreprise Online, puis exécutez l’applet de commande suivante :

```
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

Pour établir une session PowerShell distante avec Skype Entreprise Online, vous devez d’abord installer le module Skype Entreprise Online pour Windows PowerShell, que vous pouvez obtenir ici : [http://go.microsoft.com/fwlink/p/?LinkId=391911](http://go.microsoft.com/fwlink/p/?linkid=391911).

Après avoir installé le module, vous pouvez établir une session distante avec les applets de commande suivantes :

```
Import-Module LyncOnlineConnector
```
```
$cred = Get-Credential
```
```
$CSSession = New-CsOnlineSession -Credential $cred
```
```
Import-PSSession $CSSession -AllowClobber
```

Pour plus d’informations sur l’établissement d’une session PowerShell distante avec Skype Entreprise Online, reportez-vous à [Connexion à Lync Online à l’aide de Windows PowerShell](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

Pour plus d’informations sur l’utilisation du module Skype Entreprise Online PowerShell, reportez-vous à [Utilisation de Windows PowerShell pour gérer Lync Online](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

## Voir aussi

#### Autres ressources

[New-CsHostingProvider](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsHostingProvider)

