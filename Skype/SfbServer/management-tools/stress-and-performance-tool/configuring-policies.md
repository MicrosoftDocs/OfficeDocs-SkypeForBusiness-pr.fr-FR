---
title: Configuration des stratégies de l’outil de stress et de performance de Skype entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 11/11/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7e1435e2-d073-4265-8067-ebcb5bf28835
description: Configuration de la stratégie de l’outil de stress et de performance de Skype entreprise Server 2015.
ms.openlocfilehash: 5c8e4c296d06c736519a12da5b5e34c6f48e9ee2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299750"
---
# <a name="configuring-policies-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Configuration des stratégies de l’outil de stress et de performance de Skype entreprise Server 2015
 
Configuration de la stratégie de l’outil de stress et de performance de Skype entreprise Server 2015.
  
Il existe plusieurs stratégies et autres modules que vous pouvez configurer dans Skype entreprise Server 2015, avant d’exécuter l’outil stress and performance:
  
- [Stratégie d’archivage](configuring-policies.md#ArchivingPolicy)
    
- [Stratégie de conférence](configuring-policies.md#ConferencingPolicy)
    
- [Politique de contacts](configuring-policies.md#ContactsPolicy)
    
- [Stratégie de Fédération](configuring-policies.md#FederationPolicy)
    
- [Politique de contrôle d’admission des appels](configuring-policies.md#CACPolicy)
    
- [Règles de routage de la voix](configuring-policies.md#VoiceRoutingRules)
    
- [Application de surveillance de la Conférence](configuring-policies.md#ConfAttendantApp)
    
- [Service de parc d’appels serveur](configuring-policies.md#ServerCallParkServ)
    
- [Appels d’urgence](configuring-policies.md#EmergencyCalls)
    
- [Configuration de l’application Response Group](configuring-policies.md#ConfigResponseGroupApp)
    
## <a name="archiving-policy"></a>Stratégie d’archivage
<a name="ArchivingPolicy"> </a>

Si vous disposez d’un serveur d’archivage déployé dans votre topologie Skype entreprise Server, vous pouvez examiner le script ArchivingPolicy. ps1. Si vous avez besoin d’aide, consultez les applets de contrôle d’archivage et de conférence Web.
  
## <a name="conferencing-policy"></a>Stratégie de conférence
<a name="ConferencingPolicy"> </a>

Pour les conférences, nous avons le script MeetingPolicy. ps1. Si vous avez besoin d’aide, consultez les applets de contrôle de conférence Web.
  
## <a name="contacts-policy"></a>Politique de contacts
<a name="ContactsPolicy"> </a>

Le script ContactsPolicy. ps1 sera l’exemple que vous devrez revoir. Les applets de recherche et les applets de présence permettent de fournir des références supplémentaires.
  
## <a name="federation-policy"></a>Stratégie de Fédération
<a name="FederationPolicy"> </a>

L’exemple de script pour la Fédération est FederationPolicy. ps1. Les applets de contrôle, si vous avez besoin d’une analyse plus approfondie, seront serveur Edge, Fédération et accès externe.
  
## <a name="call-admission-control-policy"></a>Politique de contrôle d’admission des appels
<a name="CACPolicy"> </a>

Vous pouvez faire référence à BandwidthPolicy. ps1 pour cette stratégie. Les applets de commande de contrôle d’admission des appels comportent également des informations supplémentaires.
  
## <a name="voice-routing-rules"></a>Règles de routage de la voix
<a name="VoiceRoutingRules"> </a>

Vous aurez besoin de l’exemple de script RoutingRules. ps1 pour le routage de la voix. Lorsque vous configurez ces règles, prenez note du contexte du téléphone (c’est-à-dire le profil/location ou/SimpleName) et des codes de zone interne/externe, afin de pouvoir les spécifier lors de la création d’utilisateurs. Vous en aurez également besoin dans le cadre de la configuration de LyncPerfTool (en particulier pour PSTN-Cu et UC-RTC).
  
Par exemple, le paramètre SimpleName dans l’appel à l’applet de commande **New-CsDialPlan** dans l’exemple RoutingRules. ps1 doit être utilisé pour la valeur LocationProfile dans l’illustration suivante de UserProfileGenerator. exe:
  
![Chargez l’outil de configuration Skype Entreprise, onglet Scénarios vocaux, paramètres avancés de conversation.](../../media/59f42e4e-8f1e-4d43-9ae2-9e6026191951.png)
  
Pour plus d’informations, vous pouvez passer en revue les applets de contrôle vocales d’entreprise.
  
## <a name="conference-attendant-application"></a>Application de surveillance de la Conférence
<a name="ConfAttendantApp"> </a>

Commencez par revoir le script ConferenceAutoAttendantConfiguration. ps1. Vous devez noter le numéro de téléphone ConferencingAutoAttendant (1121111111 par défaut) pour pouvoir l’entrer dans l’outil de configuration LyncPerfTool de la génération de configuration, comme ci-dessous:
  
![Onglet Scénarios vocaux affichant le niveau de charge de la conférence et le numéro de téléphone.](../../media/a3ea5fc0-8b3d-4842-b809-f137f470dbdc.png)
  
Des informations supplémentaires sont disponibles dans les applets de connexion et les applets de service de conférence rendez-vous.
  
## <a name="server-call-park-service"></a>Service de parc d’appels serveur
<a name="ServerCallParkServ"> </a>

Ce paramètre est en fait désactivé par défaut. Vous pouvez consulter l’exemple de script CallParkConfiguration. ps1 si vous devez le tester. De plus, consultez les cmdlets de l’application de parc d’appels selon vos besoins.
  
## <a name="emergency-calls"></a>Appels d’urgence
<a name="EmergencyCalls"> </a>

Pour configurer les tests de stress et de performance des appels d’urgence, vous devez effectuer les étapes suivantes:
  
1. Configurez une gamme vocale pour les appels d’urgence. Vous pouvez utiliser le script RoutingRules. ps1, puis vérifier sous le commentaire « **routez le E911 vers PSTN** » pour obtenir un exemple de configuration de cet itinéraire vocal.
    
    > [!CAUTION]
    > La commande d’exemple dans RoutingRules. ps1 possède un modèle de nombre incluant le numéro 119 au lieu de 911. Vous devez éviter d’utiliser 911 (ou votre numéro de secours local réel) pour éviter les appels accidentels vers vos opérateurs d’urgence locaux pendant votre test de charge. N’oubliez pas que cette configuration est réservée aux fins de simulation. 
  
2. Configurez les adresses en remplissant les valeurs sous l’onglet **configuration du service d’informations d’emplacement** dans le UserProvisioningTool, comme illustré dans la figure suivante:
    
     ![Outil d’affectation d’utilisateurs affichant le nombre d’adresses, de sous-réseaux, de commutateurs et de ports.](../../media/ebe85a0c-750f-4301-97d4-d158a40ea98a.png)
  
3. Lorsque vous avez entré tout le contenu dans le UserProvisioningTool, cliquez sur le bouton **générer les fichiers de configuration de lis** .
    
4. À présent, les fichiers CSV de ports, de sous-réseaux, de commutateurs et de points d’accès sans fil (WAP), ainsi qu’un fichier XML pour l’outil de stress et de performance sera généré. Vous pouvez utiliser les fichiers CSV pour les entrées lors de la configuration du service d’information d’emplacement avec le script LisConfiguration. ps1. Pour ce faire, vous devez déplacer le fichier Locations0. xml dans le même dossier que le fichier exécutable de l’outil de stress et de performance (LyncPerfTool. exe). Cela vous permet d’exécuter des scénarios de profil d’emplacement (plan de numérotation).
    
## <a name="configuring-response-group-application"></a>Configuration de l’application Response Group
<a name="ConfigResponseGroupApp"> </a>

L’exemple de script est ResponseGroupConfiguration. ps1. Il existe également des cmdlets application de groupe de réponse à examiner pour plus d’informations sur la configuration. Le diagramme suivant montre quelques détails de la configuration:
  
![Outil de configuration de groupe de réponse affichant les flux de travail existants pour les tests.](../../media/e218a345-4813-4332-8cff-b48de05017ef.jpg)
  

