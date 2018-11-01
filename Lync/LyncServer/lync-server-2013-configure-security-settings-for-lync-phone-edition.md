---
title: Configuration des paramètres de sécurité pour Lync Phone Edition
TOCTitle: Configuration des paramètres de sécurité pour Lync Phone Edition
ms:assetid: 6e7cec17-8a79-4428-9300-8821256c46cf
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg521014(v=OCS.15)
ms:contentKeyID: 49297577
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration des paramètres de sécurité pour Lync Phone Edition

 

_**Dernière rubrique modifiée :** 2013-02-23_

Renforcez la sécurité des périphériques qui exécutent Lync Phone Edition via votre paramètre de sécurité SIP et les paramètres de verrouillage du téléphone.

## Pour configurer les paramètres de sécurité de Lync Phone Edition

1.  À partir d’un compte d’utilisateur auquel est affecté un des rôles CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Clients**, puis sur **Configuration du périphérique**.

4.  Dans la page **Configuration du périphérique**, dans la liste des configurations d’appareil, double-cliquez sur la configuration pour laquelle vous souhaitez modifier les paramètres de sécurité.

5.  Dans **Modifier la configuration du périphérique**, dans **Sécurité SIP**, spécifiez le niveau de sécurité SIP. Le niveau par défaut, que nous recommandons d’utiliser, est **Élevé**.

6.  Dans **Modifier la configuration du périphérique**, sous **Verrouillage du téléphone**, activez ou désactivez la case à cocher **Appliquer le verrouillage de l’appareil** (activée par défaut) et spécifiez la longueur minimale du code confidentiel (6 caractères par défaut) ainsi que le délai d’expiration (10 minutes par défaut). Nous recommandons d’utiliser ces valeurs par défaut ou d’augmenter la longueur du code confidentiel et/ou de diminuer le délai d’expiration.
    
    > [!NOTE]  
    > Pour plus d’informations, voir <a href="lync-server-2013-enforce-phone-locking.md">Application du verrouillage de téléphone</a>.

## Configurer les paramètres de sécurité des téléphones Lync Phone Edition à l’aide des applets de commandes Lync Server Management Shell

Il est également possible de gérer les paramètres de sécurité à l’aide de Lync Server Management Shell et de l’applet de commande **Get-CsUCPhoneConfiguration**. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session à distance de Windows PowerShell. Pour plus de détails sur l’utilisation de Windows PowerShell à distance pour une connexion à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Démarrage rapide : Gestion de Microsoft Lync Server 2010 avec PowerShell à distance » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Pour modifier le mode de sécurité SIP

  - Cette commande définit le paramètre SIPSecurityMode pour la collection globale de paramètres de téléphonie UC sur Moyen. La sécurité SIP peut également avoir le niveau Faible ou Élevé (valeur par défaut).
    
        Set-CsUCPhoneConfiguration -Identity global -SIPSecurityMode "Medium"

## Pour modifier la longueur minimale du code confidentiel

  - Dans cet exemple, tous les paramètres de téléphonie UC sont modifiés afin d’exiger une longueur minimale de 7 chiffres pour le code confidentiel.
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -MinPhonePinLength 7

Pour plus d’informations, voir [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUCPhoneConfiguration).

## Voir aussi

#### Concepts

[Gestion de l’authentification Lync Server 2013](lync-server-2013-managing-lync-server-authentication.md)  

#### Autres ressources

[Gestion des appareils, des téléphones et des applications client dans Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)

