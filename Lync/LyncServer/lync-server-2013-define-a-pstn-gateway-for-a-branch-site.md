---
title: 'Lync Server 2013 : Définition d’une passerelle RTC pour un site de succursale'
TOCTitle: Définition d’une passerelle RTC pour un site de succursale
ms:assetid: 87be2fe2-1d56-4062-b430-439d4536414c
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398689(v=OCS.15)
ms:contentKeyID: 49297982
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Définition d’une passerelle RTC pour un site de succursale dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-21_

Exécutez cette procédure sur le site central, qui doit contenir au moins un pool de serveurs frontaux ou un serveur Standard Edition.

> [!IMPORTANT]  
> Avant d’effectuer la procédure, les conditions suivantes doivent être remplies :<ul>
> <li><p>Les logiciels de communicationLync Server 2013 doivent être installés sur le site central.</p></li>
> <li><p>Le serveur de médiation doit être déployé sur le site central.</p></li></ul>


## Pour définir une passerelle RTC

1.  Cliquez sur **Démarrer** , sur **Tous les programmes** , sur **Microsoft Lync Server** , puis sur **Générateur de topologie Lync Server** .

2.  Dans l’arborescence de la console, développez le site central, développez **Sites de succursale** , développez le nom du site de succursale pour lequel définir une passerelle RTC, puis développez **Composants partagés** ..

3.  Cliquez avec le bouton droit sur **Passerelles RTC** , puis cliquez sur **Nouvelle passerelle IP/RTC** .

4.  Dans la boîte de dialogue **Définir une nouvelle passerelle IP/RTC** , cliquez sur **Passerelle FQDN ou adresse IP** , puis tapez le nom de domaine complet ou l’adresse IP de la passerelle que vous souhaitez déployer sur le site de succursale.

5.  Cliquez sur **Port d’écoute pour la passerelle IP/RTC** , puis acceptez les valeurs par défaut.

6.  Dans la liste **Protocole de transport SIP** , cliquez sur le protocole de transport utilisé par la passerelle, puis cliquez sur **OK** .
    
    > [!NOTE]  
    > Pour des raisons de sécurité, nous vous conseillons vivement d’utiliser une passerelle RTC qui prend en charge le protocole TLS (Transport Layer Security).

> [!TIP]  
> Utilisez l’applet de commande <strong>Set-CsPstnGateway</strong> pour modifier les propriétés d’une passerelle RTC. Pour plus d’informations, reportez-vous à <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsPstnGateway">Set-CsPstnGateway</a> dans l’Aide de Lync Server Management Shell.

**Étape suivante** pour la résistance d’un site de succursale : [Configuration des utilisateurs pour la résistance de sites de succursale dans Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)

## Voir aussi

#### Concepts

[Options de déploiement de passerelle RTC dans Lync Server 2013](lync-server-2013-pstn-gateway-deployment-options.md)

