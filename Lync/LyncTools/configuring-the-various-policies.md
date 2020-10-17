---
title: Configuration des différentes stratégies
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Configuring the Various Policies
ms:assetid: e3b3cbda-7c17-470b-acb0-82fdcc473184
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945610(v=OCS.15)
ms:contentKeyID: 51541436
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b0abb428dab96c09c7cd8b82d99de12ba76068eb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48505241"
---
# <a name="configuring-the-various-policies"></a>Configuration des différentes stratégies

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-24_

<div>

Voici les différentes stratégies que vous pouvez configurer dans votre topologie Lync Server 2013, avant d’exécuter l’outil de contrainte et de performances de Lync Server 2013.

<div>

## <a name="configuring-the-archiving-policy"></a>Configuration de la stratégie d’archivage

Voir l’exemple de ArchivingPolicy.ps1 de script. Vous devez utiliser ce script uniquement si un serveur d’archivage est déployé dans votre topologie. Pour plus d’informations, reportez-vous à la documentation Lync Server 2013 et à l’aide sur les cmdlets des applets de commande d' [archivage et de surveillance dans Lync Server 2013](https://technet.microsoft.com/library/gg415629\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-the-conferencing-policy"></a>Configuration de la stratégie de conférence

Voir l’exemple de MeetingPolicy.ps1 de script. Pour plus d’informations, reportez-vous à la documentation Lync Server 2013 et à l’aide relative aux cmdlets pour les applets de commande de [conférence Web dans Lync Server 2013](https://technet.microsoft.com/library/gg415675\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-the-contacts-policy"></a>Configuration de la stratégie de contacts

Voir l’exemple ContactsPolicy.ps1. Pour plus d’informations, reportez-vous à la documentation Lync Server 2013 et à l’aide relative aux applets de commande de [messagerie instantanée et de présence dans Lync Server 2013](https://technet.microsoft.com/library/gg398611\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-the-federation-policy"></a>Configuration de la stratégie de Fédération

Voir l’exemple FederationPolicy.ps1. Pour plus d’informations, reportez-vous à la documentation Lync Server 2013 et à l’aide sur les cmdlets pour les [cmdlets de serveur Edge dans Lync server 2013](https://technet.microsoft.com/library/gg415635\(v=ocs.15\)) et les applets de commande de [Fédération et d’accès externe dans Lync Server 2013](https://technet.microsoft.com/library/gg415651\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-the-call-admission-control-policy"></a>Configuration de la stratégie de contrôle d’admission des appels

Voir l’exemple BandwidthPolicy.ps1. Pour plus d’informations, reportez-vous à la vue d’ensemble de la documentation Lync Server 2013 [du contrôle d’admission des appels dans Lync server 2013](https://technet.microsoft.com/library/gg398529\(v=ocs.15\)) et de l’aide relative aux applets de [commande de contrôle d’admission des appels dans Lync Server 2013](https://technet.microsoft.com/library/gg415676\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-the-voice-routing-rules"></a>Configuration des règles de routage des communications vocales

Voir l’exemple RoutingRules.ps1. Lorsque vous configurez les règles de routage des communications vocales, notez le contexte téléphonique (autrement dit, le profil/location ou/SimpleName) et les codes de zone interne/externe afin que vous puissiez les spécifier lors de la création d’utilisateurs et de la configuration d’LyncPerfTool (spécifiquement pour PSTN-UC et UC-PSTN). Par exemple, le paramètre SimpleName dans l’appel à la cmdlet **New-CsDialPlan** dans l’exemple de RoutingRules.ps1 doit être utilisé pour la valeur LocationProfile dans la figure suivante de UserProfileGenerator.exe.

![Exemple de règle de routage des communications vocales.](images/JJ945610.9f34d971-4ed0-4a4c-b101-086a91c4578c(OCS.15).jpg "Exemple de règle de routage des communications vocales.")

Pour plus d’informations, reportez-vous à la documentation Lync Server 2013 et à l’aide sur les cmdlets pour les [applets de commande voix entreprise dans Lync Server 2013](https://technet.microsoft.com/library/gg415658\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-conferencing-attendant-application"></a>Configuration de l’application de surveillance de conférence

Voir l’exemple ConferenceAutoAttendantConfiguration.ps1. Notez le numéro de téléphone ConferencingAutoAttendant (1121111111 par défaut), afin que vous puissiez le taper dans l’outil de configuration de l’outil LyncPerf pour la génération de la configuration.

![Configuration de l’application de surveillance de conférence](images/JJ945610.0618a22f-27a9-423a-9085-d2bf71e82db6(OCS.15).jpg "Configuration de l’application de surveillance de conférence")

Pour plus d’informations, reportez-vous à la documentation Lync Server 2013 et à l’aide relative aux cmdlets pour les applets de commande de [conférence Web dans Lync server 2013](https://technet.microsoft.com/library/gg415675\(v=ocs.15\)) et [cmdlets de conférence rendez-vous dans Lync Server 2013](https://technet.microsoft.com/library/gg415630\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-lync-server-call-park-service"></a>Configuration du service de parcage d’appel Lync Server

Le parcage d’appel est désactivé par défaut. Voir l’exemple CallParkConfiguration.ps1. Pour plus d’informations, reportez-vous à la documentation Lync Server 2013 et à l’aide sur les cmdlets pour les [cmdlets d’application de parcage d’appel dans Lync Server 2013](https://technet.microsoft.com/library/gg415639\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-emergency-calls"></a>Configuration des appels d’urgence

Procédez comme suit pour configurer les tests de contrainte et de performances pour les appels d’urgence.

1.  Configurer un itinéraire des communications vocales pour les appels d’urgence. Consultez le script de RoutingRules.ps1 sous le commentaire « route E911 to RTC » pour obtenir un exemple de configuration de cet itinéraire des communications vocales.
    
    <div>
    

    > [!WARNING]  
    > La commande de l’exemple dans RoutingRules.ps1 a un modèle de numéro qui inclut le numéro 119 au lieu de 911. Vous devez éviter d’utiliser 911 (ou votre numéro d’urgence local réel) pour éviter les appels accidentels à vos opérateurs d’urgence locaux pendant les tests de charge. Cette configuration est destinée uniquement à des fins de simulation.

    
    </div>

2.  Configurez les adresses en remplissant les valeurs de l’onglet **lis** dans le UserProvisioningTool, comme illustré dans la figure suivante.
    
    ![Configuration du service informations d’emplacement.](images/JJ945610.8ac1faa1-e9f9-40d0-b8b7-b159f4f459f7(OCS.15).jpg "Configuration du service informations d’emplacement.")  

3.  Cliquez sur **générer des fichiers de configuration lis**.

4.  Les fichiers CSV pour les ports, les sous-réseaux, les commutateurs et les points d’accès sans fil (WAP), ainsi qu’un fichier XML pour l’outil de contrainte et de performances de Lync Server 2013, sont générés. Les fichiers CSV doivent être utilisés comme entrées (dans le même dossier) lors de la configuration de LIS (location Information Service) avec le script LisConfiguration.ps1. Déplacez le fichier de Locations0.xml généré dans le même dossier que le fichier exécutable de l’outil stress and performance Lync Server 2013 (LyncPerfTool.exe), qui exécutera les scénarios de profil d’emplacement (plan de numérotation).

</div>

<div>

## <a name="creating-enabling-configuring-and-disabling-users"></a>Création, activation, configuration et désactivation des utilisateurs

Vous devez créer tous les utilisateurs avant d’exécuter les scripts suivants. Suivez les instructions de la procédure [créer des utilisateurs et des contacts](create-users-and-contacts.md) pour créer des utilisateurs. Pour plus d’informations, reportez-vous à la documentation de l’applet de commande Lync Server 2013 pour les cmdlets [Get-Csuser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)), [Set-Csuser](https://technet.microsoft.com/library/gg398510\(v=ocs.15\))et [Disable-Csuser](https://technet.microsoft.com/library/gg398747\(v=ocs.15\)) .

</div>

<div>

## <a name="configuring-response-group-application"></a>Configuration de l’application Response Group

Voir l’exemple ResponseGroupConfiguration.ps1. Pour plus d’informations, reportez-vous à la documentation Lync Server 2013 et à l’aide sur les cmdlets pour les [cmdlets application Response Group dans Lync Server 2013](https://technet.microsoft.com/library/gg415654\(v=ocs.15\)). Pour examiner la configuration de l’application Response Group, voir `https://<poolfqdn>/RgsConfig/` , comme illustré dans la figure suivante.

![Outil de configuration Response Group.](images/JJ945610.480a9440-2283-4533-98f8-86daaab4781c(OCS.15).jpg "Outil de configuration Response Group.")

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

