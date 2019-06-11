---
title: Configuration de diverses stratégies
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Configuring the Various Policies
ms:assetid: e3b3cbda-7c17-470b-acb0-82fdcc473184
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945610(v=OCS.15)
ms:contentKeyID: 51541436
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a105ea62b82d904007a2faa0493fd17092b84462
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839051"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-various-policies"></a>Configuration de diverses stratégies

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-24_

<div>

## <a name="configuring-the-various-policies"></a>Configuration de diverses stratégies

Voici les différentes stratégies que vous pouvez configurer dans votre topologie Lync Server 2013 avant d’exécuter l’outil de stress et de performance de Lync Server 2013.

<div>

## <a name="configuring-the-archiving-policy"></a>Configuration de la stratégie d’archivage

Consultez l’exemple de script ArchivingPolicy. ps1. Vous devez utiliser ce script uniquement si un serveur d’archivage est déployé dans votre topologie. Pour plus d’informations, reportez-vous à la documentation de Lync Server 2013 et à l’aide de l’applet de [contrôle dans Lync server 2013](https://technet.microsoft.com/en-us/library/gg415629\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-the-conferencing-policy"></a>Configuration de la stratégie de conférence

Consultez l’exemple de script MeetingPolicy. ps1. Pour plus d’informations, reportez-vous à la documentation de Lync Server 2013 et à l’aide de l’applet de cmdlet pour les applets de connexion [Web dans Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415675\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-the-contacts-policy"></a>Configuration de la stratégie de contacts

Consultez l’exemple ContactsPolicy. ps1. Pour plus d’informations, reportez-vous à la documentation de Lync Server 2013 et à l’aide sur les applets de connexion [dans Lync Server 2013](https://technet.microsoft.com/en-us/library/gg398611\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-the-federation-policy"></a>Configuration de la stratégie de Fédération

Consultez l’exemple FederationPolicy. ps1. Pour plus d’informations, reportez-vous à la documentation de Lync Server 2013 et à l’aide sur les applets de connexion [dans Lync server 2013](https://technet.microsoft.com/en-us/library/gg415635\(v=ocs.15\)) et les applets de connexion [et accès externe dans Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415651\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-the-call-admission-control-policy"></a>Configuration de la stratégie de contrôle d’admission des appels

Consultez l’exemple BandwidthPolicy. ps1. Pour plus d’informations, reportez-vous à la vue d’ensemble de la documentation Lync Server 2013 [du contrôle d’admission des appels dans Lync server 2013](https://technet.microsoft.com/en-us/library/gg398529\(v=ocs.15\)) et l’aide de l’applet de commande pour les applets de [commande d’admission des appels dans Lync 2013 Server](https://technet.microsoft.com/en-us/library/gg415676\(v=ocs.15\))

</div>

<div>

## <a name="configuring-the-voice-routing-rules"></a>Configuration des règles de routage de la voix

Consultez l’exemple RoutingRules. ps1. Lorsque vous configurez les règles de routage vocal, prenez note du contexte du téléphone (c’est-à-dire, du profil/location ou/SimpleName) et des indicatifs de zone externes/externes pour pouvoir les spécifier lors de la création d’utilisateurs et de la configuration d’LyncPerfTool (en particulier pour RTC et UC-RTC). Par exemple, le paramètre SimpleName dans l’appel à l’applet de commande **New-CsDialPlan** dans l’exemple RoutingRules. ps1 doit être utilisé pour la valeur LocationProfile dans l’illustration suivante de UserProfileGenerator. exe.

![Exemple de règle de routage vocal.] (images/JJ945610.9f34d971-4ed0-4a4c-b101-086a91c4578c(OCS.15).jpg "Exemple de règle de routage vocal.")

Pour plus d’informations, reportez-vous à la documentation de Lync Server 2013 et à l’aide de l’applet de cmdlet pour les [applets de connexion voix entreprise dans Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415658\(v=ocs.15\))

</div>

<div>

## <a name="configuring-conferencing-attendant-application"></a>Configuration de l’application de surveillance des conférences

Consultez l’exemple ConferenceAutoAttendantConfiguration. ps1. Prenez note du numéro de téléphone ConferencingAutoAttendant (1121111111, par défaut), afin de pouvoir le taper dans l’outil de configuration des outils LyncPerf pour la génération de configuration.

![Configuration de l’application de surveillance des conférences] (images/JJ945610.0618a22f-27a9-423a-9085-d2bf71e82db6(OCS.15).jpg "Configuration de l’application de surveillance des conférences")

Pour plus d’informations, reportez-vous à la documentation de Lync Server 2013 et à l’aide de l’applet de cmdlet pour les applets de connexion [Web dans Lync server 2013](https://technet.microsoft.com/en-us/library/gg415675\(v=ocs.15\)) et les [applets de service de conférence rendez-vous dans Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415630\(v=ocs.15\))

</div>

<div>

## <a name="configuring-lync-server-call-park-service"></a>Configuration du service de parc d’appels Lync Server

Le parc d’appels est désactivé par défaut. Consultez l’exemple CallParkConfiguration. ps1. Pour plus d’informations, reportez-vous à la documentation de Lync Server 2013 et à l’aide de l’applet de cmdlet pour les applets de connexion de l' [application Park dans Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415639\(v=ocs.15\))

</div>

<div>

## <a name="configuring-emergency-calls"></a>Configuration des appels d’urgence

Suivez les étapes ci-dessous pour configurer le test de stress et de performance des appels d’urgence.

1.  Configurez une gamme vocale pour les appels d’urgence. Voir le script RoutingRules. ps1 sous le commentaire «route de E911 vers PSTN» pour obtenir un exemple de configuration de ce routage.
    
    <div>
    

    > [!WARNING]  
    > La commande d’exemple dans RoutingRules. ps1 possède un modèle de nombre incluant le numéro 119 au lieu de 911. Vous devez éviter d’utiliser 911 (ou votre numéro de secours local réel) pour éviter les appels accidentels vers vos opérateurs d’urgence locaux pendant le test de charge. Cette configuration s’utilise uniquement à des fins de simulation.

    
    </div>

2.  Configurez les adresses en remplissant les valeurs sous l’onglet **lis** dans UserProvisioningTool, comme illustré dans la figure ci-dessous.
    
    ![Configuration du service d’information d’emplacement.] (images/JJ945610.8ac1faa1-e9f9-40d0-b8b7-b159f4f459f7(OCS.15).jpg "Configuration du service d’information d’emplacement.")  

3.  Cliquez sur **générer les fichiers de configuration de lis**.

4.  Les fichiers CSV pour les ports, les sous-réseaux, les commutateurs et les points d’accès sans fil (WAP) et un fichier XML pour l’outil de stress et de performance Lync Server 2013 sont générés. Les fichiers CSV doivent être utilisés en tant qu’entrées (dans le même dossier) lors de la configuration du service d’information d’emplacement (LIS) avec le script LisConfiguration. ps1. Déplacez le fichier Locations0. XML généré vers le même dossier que le fichier exécutable de l’outil de stress et de performance Lync Server 2013 (LyncPerfTool. exe), qui s’exécute dans les scénarios de profil d’emplacement (plan de numérotation).

</div>

<div>

## <a name="creating-enabling-configuring-and-disabling-users"></a>Création, activation, configuration et désactivation des utilisateurs

Vous devez créer tous vos utilisateurs avant d’exécuter les scripts suivants. Pour créer des utilisateurs, suivez les instructions de la procédure [créer des utilisateurs et des contacts](create-users-and-contacts.md) . Pour plus d’informations, reportez-vous à la documentation sur l’applet de passe Lync Server 2013 pour les applets de connexion [Get-Csuser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)), [Set-Csuser](https://technet.microsoft.com/en-us/library/gg398510\(v=ocs.15\))et [Disable-Csuser](https://technet.microsoft.com/en-us/library/gg398747\(v=ocs.15\)) .

</div>

<div>

## <a name="configuring-response-group-application"></a>Configuration de l’application Response Group

Consultez l’exemple ResponseGroupConfiguration. ps1. Pour plus d’informations, reportez-vous à la documentation de Lync Server 2013 et à l’aide de l’applet de cmdlet pour les applets de [demande de groupe de réponse dans Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415654\(v=ocs.15\)) Pour passer en revue la configuration de l’application `https://<poolfqdn>/RgsConfig/`Response Group, voir, comme illustré dans la figure ci-dessous.

![Outil de configuration de Response Group.] (images/JJ945610.480a9440-2283-4533-98f8-86daaab4781c(OCS.15).jpg "Outil de configuration de Response Group.")

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

