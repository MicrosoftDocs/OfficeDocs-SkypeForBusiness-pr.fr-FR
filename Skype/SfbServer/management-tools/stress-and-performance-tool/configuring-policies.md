---
title: Configuration des stratégies pour le Skype pour Business Server 2015 Stress et l’outil performances
ms.author: heidip
author: microsoftheidi
ms.date: 11/11/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7e1435e2-d073-4265-8067-ebcb5bf28835
description: Configuration de la stratégie de Skype pour Business Server 2015 Stress et l’outil performances.
ms.openlocfilehash: 5bdeb4c65b3649e7d417550578e277e01e55fcc3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="configuring-policies-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Configuration des stratégies pour le Skype pour Business Server 2015 Stress et l’outil performances
 
Configuration de la stratégie de Skype pour Business Server 2015 Stress et l’outil performances.
  
Il existe plusieurs stratégies et autres zones que vous pouvez configurer dans Skype pour 2015 de serveur d’entreprise, avant d’exécuter l’outil de performances et le Stress :
  
- [Stratégie d’archivage](configuring-policies.md#ArchivingPolicy)
    
- [Stratégie de conférence](configuring-policies.md#ConferencingPolicy)
    
- [Stratégie des contacts](configuring-policies.md#ContactsPolicy)
    
- [Stratégie de fédération](configuring-policies.md#FederationPolicy)
    
- [Politique de contrôle d’Admission des appels](configuring-policies.md#CACPolicy)
    
- [Règles de routage de voix](configuring-policies.md#VoiceRoutingRules)
    
- [Application de surveillance du conférence](configuring-policies.md#ConfAttendantApp)
    
- [Service de serveur appel Park](configuring-policies.md#ServerCallParkServ)
    
- [Appels d’urgence](configuring-policies.md#EmergencyCalls)
    
- [Application de la configuration de groupe de réponse](configuring-policies.md#ConfigResponseGroupApp)
    
## <a name="archiving-policy"></a>Stratégie d’archivage
<a name="ArchivingPolicy"> </a>

Si vous disposez d’un serveur d’archivage déployé dans votre Skype pour la topologie du serveur de l’entreprise, vous pouvez consulter le script ArchivingPolicy.ps1. Si vous avez besoin d’une assistance supplémentaire, consultez les applets de commande d’archivage et de conférence Web.
  
## <a name="conferencing-policy"></a>Stratégie de conférence
<a name="ConferencingPolicy"> </a>

Pour la conférence, nous avons le script MeetingPolicy.ps1. Si vous avez besoin d’une assistance supplémentaire, consultez les applets de commande de conférences sur le Web.
  
## <a name="contacts-policy"></a>Stratégie des contacts
<a name="ContactsPolicy"> </a>

Script de ContactsPolicy.ps1 est l’exemple que vous devez passer en revue. Si vous avez besoin plus de références vous aide aux applets de commande de messagerie instantanée et de présence.
  
## <a name="federation-policy"></a>Stratégie de fédération
<a name="FederationPolicy"> </a>

L’exemple de script pour la fédération est FederationPolicy.ps1. Les applets de commande à passer en revue, si vous avez besoin d’insight, sera de serveur de transport Edge, la fédération et l’accès externe.
  
## <a name="call-admission-control-policy"></a>Politique de contrôle d’Admission des appels
<a name="CACPolicy"> </a>

Vous pouvez faire référence à BandwidthPolicy.ps1 pour cette stratégie. Les applets de commande de contrôle d’Admission appel aura davantage d’informations ainsi.
  
## <a name="voice-routing-rules"></a>Règles de routage de voix
<a name="VoiceRoutingRules"> </a>

Vous aurez besoin de l’exemple de script RoutingRules.ps1 pour le routage des communications vocales. Lorsque vous configurez ces règles, prenez note du contexte téléphonique (c'est-à-dire /Location profil ou /SimpleName) et les Codes de zone interne/externe, afin que vous pouvez les spécifier lors de la création d’utilisateurs. Vous allez également besoin lors de la configuration de LyncPerfTool (spécifiquement pour RTPC-UC et les communications unifiées-PSTN).
  
Par exemple, le paramètre SimpleName dans l’appel à l’applet de commande **New-CsDialPlan** dans l’exemple RoutingRules.ps1 doit être utilisé pour la valeur de LocationProfile dans la figure suivante de UserProfileGenerator.exe :
  
![Chargez l’outil de configuration Skype Entreprise, onglet Scénarios vocaux, paramètres avancés de conversation.](../../media/59f42e4e-8f1e-4d43-9ae2-9e6026191951.png)
  
Pour plus d’informations, vous pouvez consulter les applets de commande Voix Entreprise.
  
## <a name="conference-attendant-application"></a>Application de surveillance du conférence
<a name="ConfAttendantApp"> </a>

Tout d’abord, examinez le script ConferenceAutoAttendantConfiguration.ps1. Vous allez, si vous le souhaitez, notez le numéro de téléphone de ConferencingAutoAttendant (1121111111 par défaut), afin que vous pouvez l’entrer dans l’outil de configuration de LyncPerfTool pour la génération de la configuration, comme indiqué ci-dessous :
  
![Onglet Scénarios vocaux affichant le niveau de charge de la conférence et le numéro de téléphone.](../../media/a3ea5fc0-8b3d-4842-b809-f137f470dbdc.png)
  
Vous trouverez plus de détails de la conférence et les conférences à distance applets de commande.
  
## <a name="server-call-park-service"></a>Service de serveur appel Park
<a name="ServerCallParkServ"> </a>

En fait, il est désactivé par défaut. Vous pouvez consulter l’exemple de script CallParkConfiguration.ps1 si vous avez besoin effectuer ce test. En outre, Découvrez les applets de commande d’appeler une Application de parc selon vos besoins.
  
## <a name="emergency-calls"></a>Appels d’urgence
<a name="EmergencyCalls"> </a>

Vous devez effectuer les étapes suivantes pour configurer le stress et le test de performance pour les appels d’urgence :
  
1. Configurer un itinéraire de voix pour les appels d’urgence. Vous pouvez utiliser le script RoutingRules.ps1 et vérifiez sous le commentaire « **E911 itinéraire vers RTPC** » pour obtenir un exemple de la façon de configurer cet itinéraire de voix.
    
    > [!CAUTION]
    > L’exemple de commande de RoutingRules.ps1 a un modèle de numéro qui inclut le numéro 119 plutôt que 911. Vous devez éviter d’utiliser le 911 (ou votre numéro d’urgence local réel) afin d’éviter des appels accidentelles à vos opérateurs d’urgence locales pendant votre test de charge. N’oubliez pas que cette configuration est uniquement à des fins de simulation ! 
  
2. Configurer les adresses en renseignant les valeurs dans l’onglet **Configuration du Service Info emplacement** dans la UserProvisioningTool, comme illustré dans la figure suivante :
    
     ![Outil d’affectation d’utilisateurs affichant le nombre d’adresses, de sous-réseaux, de commutateurs et de ports.](../../media/ebe85a0c-750f-4301-97d4-d158a40ea98a.png)
  
3. Lorsque vous avez saisi tous les éléments dans le UserProvisioningTool, cliquez sur le bouton de **Génération de fichiers Config de LIS** .
    
4. Désormais les fichiers CSV pour les ports, les sous-réseaux, les commutateurs et les points d’accès sans fil (WAP), ainsi que d’un fichier XML pour l’outil de Stress and Performance sera généré. Vous pouvez utiliser les fichiers CSV des entrées lors de la configuration du service d’informations d’emplacement (LIS) avec le script LisConfiguration.ps1. Pour ce faire, vous devez déplacer le fichier Locations0.xml dans le même dossier que le Stress et les performances, outil exécutable (LyncPerfTool.exe). Cela vous permettra d’exécuter des scénarios de profil (plan de numérotation) emplacement.
    
## <a name="configuring-response-group-application"></a>Application de la configuration de groupe de réponse
<a name="ConfigResponseGroupApp"> </a>

L’exemple de script est ResponseGroupConfiguration.ps1. Il existe également des applets de commande groupe réponse application à consulter pour obtenir les détails de configuration. Le diagramme suivant affiche certains détails de la configuration :
  
![Outil de configuration de groupe de réponse affichant les flux de travail existants pour les tests.](../../media/e218a345-4813-4332-8cff-b48de05017ef.jpg)
  

