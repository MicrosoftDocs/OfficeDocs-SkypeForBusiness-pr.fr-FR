---
title: Affichage des paramètres de configuration de Lync Phone Edition
TOCTitle: Affichage des paramètres de configuration de Lync Phone Edition
ms:assetid: 15f94478-651f-4063-9918-6a059f98df16
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ687976(v=OCS.15)
ms:contentKeyID: 49891243
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Affichage des paramètres de configuration de Lync Phone Edition

 

_**Dernière rubrique modifiée :** 2013-02-23_

Vous pouvez afficher des informations sur la configuration des périphériques qui exécutent Lync Phone Edition. Les informations sont classées dans des collections. Lorsque vous installez Lync Server, vous obtenez une collection de paramètres Lync Phone Edition qui s’applique à tous les périphériques exécutant Lync Phone Edition dans votre déploiement. Vous pouvez également créer de nouvelles collections de paramètres pour un site en particulier. Les paramètres du site ont priorité sur les paramètres globaux. Chaque collection de paramètres se compose d’un nom, de l’étendue (globale ou de site), du paramètre de sécurité SIP, du niveau de journalisation, du niveau de qualité de service de la voix (QoS), du paramètre de verrouillage du téléphone et des détails de verrouillage du téléphone, c’est-à-dire la longueur minimale du code confidentiel de déverrouillage et le délai avant le verrouillage automatique du téléphone.

## Pour afficher des informations sur la configuration des périphériques exécutant Lync Phone Edition

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Clients**, puis sur le bouton de navigation **Configuration du périphérique**.

4.  Dans la page **Configuration du périphérique**, cliquez sur la collection de paramètres sur laquelle vous souhaitez afficher des informations. Le nom, l’étendue, le paramètre de sécurité SIP, le niveau de qualité de service de la voix et le paramètre de verrouillage du téléphone sont répertoriés dans la page principale. Pour afficher le niveau de journalisation et les détails de verrouillage du téléphone, cliquez sur le menu **Edition**, puis sur **Afficher les détails**.

## Pour afficher des informations sur la configuration de Lync Phone Edition à l’aide des applets de commande Lync Server Management Shell

Vous pouvez également afficher les paramètres de configuration de Lync Phone Edition à l’aide des applets de commande Lync Server Management Shell et **Get-CsUCPhoneConfiguration**. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Pour afficher des informations sur la configuration de Lync Phone Edition

  - Pour afficher des informations sur tous vos paramètres de configuration Lync Phone Edition, tapez la commande suivante dans Lync Server Management Shell et appuyez sur ENTRÉE :
    
        Get-CsUCPhoneConfiguration
    
    La commande renvoie les informations suivantes :
    
        Identity             : Global
        CalendarPollInterval : 00:03:00
        EnforcePhoneLock     : True
        PhoneLockTimeout     : 00:10:00
        MinPhonePinLength    : 6
        SIPSecurityMode      : High
        VoiceDiffServTag     : 40
        Voice8021p           : 0
        LoggingLevel         : Off

Pour plus d’informations, voir [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUCPhoneConfiguration).

## Voir aussi

#### Tâches

[Création ou modification d’une collection de paramètres de configuration de Lync Phone Edition](lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md)  
[Suppression d’une collection existante de paramètres de configuration Lync Phone Edition](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[Configuration des paramètres de sécurité pour Lync Phone Edition](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[Application du verrouillage de téléphone](lync-server-2013-enforce-phone-locking.md)

