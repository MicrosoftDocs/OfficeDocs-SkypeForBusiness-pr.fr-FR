---
title: Application du verrouillage de téléphone
TOCTitle: Application du verrouillage de téléphone
ms:assetid: 1f89298b-aea9-4952-93ca-0270b565792b
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg520963(v=OCS.15)
ms:contentKeyID: 49296458
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Application du verrouillage de téléphone

 

_**Dernière rubrique modifiée :** 2013-02-23_

Il est possible de verrouiller les périphériques Lync Phone Edition à des fins de sécurité. Si vous appliquez le verrouillage du téléphone, le périphérique exécutant Lync Phone Edition se verrouille après une période configurée par vos soins. Quand un téléphone est verrouillé, un utilisateur peut passer des appels, mais il ne peut pas accéder aux informations de calendrier et de contact, à la messagerie vocale ou aux journaux des appels, ni utiliser la recherche. Pour déverrouiller le téléphone, l’utilisateur entre un code confidentiel.

Pour appliquer le verrouillage du téléphone, activez-le et configurez-le à l’aide du Panneau de configuration de Lync Server ou des applets de commande PowerShell de Lync Server. Vous pouvez appliquer le verrouillage du téléphone globalement ou le limiter au site pour lequel il est configuré.

## Pour configurer et appliquer le verrouillage du téléphone

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Cliquez sur **Clients**, puis sur **Configuration du périphérique**.

4.  Sous l’onglet **Configuration du périphérique**, dans la liste des configurations possibles, double-cliquez sur la configuration pour laquelle vous souhaitez modifier les paramètres de verrouillage du téléphone.

5.  Dans la boîte de dialogue **Modifier la configuration du périphérique**, vérifiez que la case à cocher **Appliquer le verrouillage de l’appareil** est activée.

6.  Dans **Longueur minimale du code confidentiel**, acceptez la valeur par défaut pour le nombre minimum de chiffres que doit contenir le code confidentiel de déverrouillage ou spécifiez une nouvelle valeur. Ce code peut être constitué de quatre à quinze chiffres et la longueur par défaut est six chiffres.

7.  Dans **Délai d’expiration du verrouillage du téléphone**, acceptez la valeur par défaut pour le délai minimal avant le verrouillage automatique du téléphone ou spécifiez une nouvelle valeur. Ce délai est compris entre 0 et 60 minutes et la valeur par défaut est 10. Le format de cette valeur est HH:MM:SS.

8.  Cliquez sur **Valider**.

## Application du verrouillage du téléphone à l’aide des applets de commande Windows PowerShell

Le verrouillage du téléphone peut être appliqué à l’aide de l’applet de commande Set-CsUCPhoneConfiguration. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Pour activer le verrouillage du téléphone

  - La commande suivante active le verrouillage du téléphone sur le site de Redmond. Pour désactiver le verrouillage du téléphone, attribuez à la propriété EnforcePhoneLock la valeur Faux ($False).
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True

## Pour activer le verrouillage du téléphone et modifier le délai d’expiration du verrouillage du téléphone

  - Cette commande active le verrouillage du téléphone et définit également le délai d’expiration du verrouillage sur 30 minutes.
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True -PhoneLockTimeout "00:30:00"

## Pour activer le verrouillage du téléphone dans l’organisation

  - Dans cet exemple, le verrouillage du téléphone est activé sur les paramètres de configuration de tous les téléphones UC utilisés dans l’organisation.
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration  -EnforcePhoneLock $True

Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Set-CsUCPhoneConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsUCPhoneConfiguration).

## Voir aussi

#### Concepts

[Gestion de l’authentification Lync Server 2013](lync-server-2013-managing-lync-server-authentication.md)  

#### Autres ressources

[Gestion des appareils, des téléphones et des applications client dans Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)

