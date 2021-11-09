---
title: Configuration des stratégies pour l Skype Entreprise Server 2015 Stress and Performance Tool
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
ms.date: 11/11/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 7e1435e2-d073-4265-8067-ebcb5bf28835
description: Configuration de stratégie pour Skype Entreprise Server 2015 Stress and Performance Tool.
ms.openlocfilehash: 3bf593402340386e21a2cc339b6eb971c7bbd39f
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60857321"
---
# <a name="configuring-policies-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Configuration des stratégies pour l Skype Entreprise Server 2015 Stress and Performance Tool
 
Configuration de stratégie pour Skype Entreprise Server 2015 Stress and Performance Tool.
  
Vous pouvez configurer plusieurs stratégies et autres domaines dans Skype Entreprise Server 2015 avant d’utiliser l’outil Stress and Performance :
  
- [Stratégie d’archivage](configuring-policies.md#ArchivingPolicy)
    
- [Stratégie de conférence](configuring-policies.md#ConferencingPolicy)
    
- [Stratégie de contacts](configuring-policies.md#ContactsPolicy)
    
- [Stratégie de fédération](configuring-policies.md#FederationPolicy)
    
- [Stratégie de contrôle d’admission des appels](configuring-policies.md#CACPolicy)
    
- [Règles de routage des voix](configuring-policies.md#VoiceRoutingRules)
    
- [Application Conference Attendant](configuring-policies.md#ConfAttendantApp)
    
- [Service de parc d’appel serveur](configuring-policies.md#ServerCallParkServ)
    
- [Appels d’urgence](configuring-policies.md#EmergencyCalls)
    
- [Configuration de l’application Response Group](configuring-policies.md#ConfigResponseGroupApp)
    
## <a name="archiving-policy"></a>Stratégie d’archivage
<a name="ArchivingPolicy"> </a>

Si vous avez un serveur d’archivage déployé dans votre topologie Skype Entreprise Server, vous pouvez examiner le script ArchivingPolicy.ps1'archivage. Si vous avez besoin d’une assistance supplémentaire, consultez les cmdlets d’archivage et de conférence Web.
  
## <a name="conferencing-policy"></a>Stratégie de conférence
<a name="ConferencingPolicy"> </a>

Pour les conférences, nous avons le script MeetingPolicy.ps1 de conférence. Si vous avez besoin d’une assistance supplémentaire, consultez les cmdlets de conférence web.
  
## <a name="contacts-policy"></a>Stratégie de contacts
<a name="ContactsPolicy"> </a>

ContactsPolicy.ps1 script sera l’exemple que vous devrez examiner. Les cmdlets de messagerie instantanée et de présence vous aideront si vous avez besoin de références supplémentaires.
  
## <a name="federation-policy"></a>Stratégie de fédération
<a name="FederationPolicy"> </a>

L’exemple de script pour la fédération est FederationPolicy.ps1. Les cmdlets à examiner, si vous avez besoin d’informations supplémentaires, seront le serveur Edge, la fédération et l’accès externe.
  
## <a name="call-admission-control-policy"></a>Stratégie de contrôle d’admission des appels
<a name="CACPolicy"> </a>

Vous pouvez référencer BandwidthPolicy.ps1 pour cette stratégie. Les cmdlets du contrôle d’admission des appels auront également des informations supplémentaires.
  
## <a name="voice-routing-rules"></a>Règles de routage des voix
<a name="VoiceRoutingRules"> </a>

Vous aurez besoin de l’exemple RoutingRules.ps1 script pour le routage des voix. Lorsque vous configurez ces règles, prenez note du contexte téléphonique (c’est-à-dire, /Location Profile ou /SimpleName) et des codes de zone interne/externe, afin de pouvoir les spécifier lors de la création d’utilisateurs. Vous en aurez également besoin lors de la configuration de LyncPerfTool (spécifiquement pour PSTN-UC et UC-PSTN).
  
Par exemple, le paramètre SimpleName dans l’appel à l’cmdlet **New-CsDialPlan** dans l’exemple RoutingRules.ps1 doit être utilisé pour la valeur LocationProfile dans la figure suivante de UserProfileGenerator.exe :
  
![Skype Entreprise outil de configuration de chargement, onglet Scénarios vocaux, Paramètres avancés des conversations.](../../media/59f42e4e-8f1e-4d43-9ae2-9e6026191951.png)
  
Pour plus d’informations, vous pouvez consulter les Voix Entreprise cmdlets.
  
## <a name="conference-attendant-application"></a>Application Conference Attendant
<a name="ConfAttendantApp"> </a>

Tout d’abord, examinez ConferenceAutoAttendantConfiguration.ps1 script. Notez le numéro de téléphone ConferencingAutoAttendant (1121111111 par défaut), afin de pouvoir l’entrer dans l’outil de configuration LyncPerfTool pour la génération de configuration, comme ci-dessous :
  
![Onglet Scénarios de voix affichant le niveau de charge de conférence et le numéro de téléphone.](../../media/a3ea5fc0-8b3d-4842-b809-f137f470dbdc.png)
  
Vous trouverez plus d’informations dans les cmdlets conférence et conférences téléphoniques.
  
## <a name="server-call-park-service"></a>Service de parc d’appel serveur
<a name="ServerCallParkServ"> </a>

Cette option est en fait désactivée par défaut. Vous pouvez consulter l'CallParkConfiguration.ps1 exemple de script si vous devez le tester. En outre, consultez les cmdlets d’application de parcage d’appel si nécessaire.
  
## <a name="emergency-calls"></a>Appels d’urgence
<a name="EmergencyCalls"> </a>

Vous devez effectuer les étapes suivantes pour configurer le test de contrainte et de performances pour les appels d’urgence :
  
1. Configurer un itinéraire de voix pour les appels d’urgence. Vous pouvez utiliser le script RoutingRules.ps1 et vérifier sous le commentaire « **Router E911 vers PSTN** » pour obtenir un exemple de la façon de configurer cet itinéraire de voix.
    
    > [!CAUTION]
    > L’exemple de commande RoutingRules.ps1 a un modèle de numéro qui inclut le numéro 119 au lieu de 911. Évitez d’utiliser le 911 (ou votre numéro d’urgence local réel) pour éviter les appels accidentels vers vos opérateurs d’urgence locaux pendant les tests de charge. N’oubliez pas que cette configuration est uniquement à des fins de simulation ! 
  
2. Configurez les adresses en remplissant les valeurs sous l’onglet Configuration du **service** d’informations d’emplacement dans UserProvisioningTool, comme illustré dans la figure suivante :
    
     ![Outil d’approvisionnement utilisateur affichant le nombre d’adresses, de sous-réseaux, de commutateurs et de ports.](../../media/ebe85a0c-750f-4301-97d4-d158a40ea98a.png)
  
3. Une fois que vous avez entré tous les fichiers dans UserProvisioningTool, cliquez sur le bouton Générer des fichiers de **config LIS.**
    
4. Désormais, des fichiers CSV pour les ports, sous-réseaux, commutateurs et points d’accès sans fil, ainsi qu’un fichier XML pour l’outil Stress and Performance seront générés. Vous pouvez utiliser les fichiers CSV pour les entrées lors de la configuration du service LIS (Location Information Service) avec LisConfiguration.ps1 script. Pour ce faire, vous devez déplacer le fichier Locations0.xml vers le même dossier que le fichier exécutable de l’outil Stress and Performance (LyncPerfTool.exe). Cela vous permettra d’exécuter des scénarios de profil d’emplacement (plan de numérotation).
    
## <a name="configuring-response-group-application"></a>Configuration de l’application Response Group
<a name="ConfigResponseGroupApp"> </a>

L’exemple de script est ResponseGroupConfiguration.ps1. Il existe également des cmdlets d’application Response Group à examiner pour obtenir des détails supplémentaires sur la configuration. Le diagramme suivant présente certains détails de configuration :
  
![Outil de config Response Group montrant les flux de travail existants à tester.](../../media/e218a345-4813-4332-8cff-b48de05017ef.jpg)
  

