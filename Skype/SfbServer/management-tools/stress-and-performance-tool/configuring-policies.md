---
title: Configuration des stratégies pour le Skype pour Business Server 2015 Stress and Performance Tool
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
ms.date: 11/11/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7e1435e2-d073-4265-8067-ebcb5bf28835
description: Configuration de la stratégie de Skype pour Business Server 2015 Stress and Performance Tool.
ms.openlocfilehash: c5dd20df0cac3121169f6eb5659eb6339d7875e2
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32236170"
---
# <a name="configuring-policies-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Configuration des stratégies pour le Skype pour Business Server 2015 Stress and Performance Tool
 
Configuration de la stratégie de Skype pour Business Server 2015 Stress and Performance Tool.
  
Il existe plusieurs stratégies et autres domaines que vous pouvez configurer dans Skype pour Business Server 2015, avant d’exécuter le Stress and Performance Tool :
  
- [Stratégie d’archivage](configuring-policies.md#ArchivingPolicy)
    
- [Stratégie de conférence](configuring-policies.md#ConferencingPolicy)
    
- [Stratégie de contacts](configuring-policies.md#ContactsPolicy)
    
- [Stratégie de fédération](configuring-policies.md#FederationPolicy)
    
- [Politique de contrôle d’admission des appels](configuring-policies.md#CACPolicy)
    
- [Règles de routage voix](configuring-policies.md#VoiceRoutingRules)
    
- [Application intendant Conférence](configuring-policies.md#ConfAttendantApp)
    
- [Service de parcage d’appel de serveur](configuring-policies.md#ServerCallParkServ)
    
- [Appels d’urgence](configuring-policies.md#EmergencyCalls)
    
- [Application de configuration Response Group](configuring-policies.md#ConfigResponseGroupApp)
    
## <a name="archiving-policy"></a>Stratégie d’archivage
<a name="ArchivingPolicy"> </a>

Si vous disposez d’un serveur d’archivage déployé dans votre Skype pour la topologie du serveur d’entreprise, vous pouvez consulter le script ArchivingPolicy.ps1. Si vous avez besoin d’aide, consultez la rubrique les applets de commande d’archivage et de conférence Web.
  
## <a name="conferencing-policy"></a>Stratégie de conférence
<a name="ConferencingPolicy"> </a>

Pour la conférence, nous avons le script MeetingPolicy.ps1. Si vous avez besoin d’aide, consultez la rubrique les applets de commande de conférence Web.
  
## <a name="contacts-policy"></a>Stratégie de contacts
<a name="ContactsPolicy"> </a>

Script ContactsPolicy.ps1 sera l’exemple, que vous devrez consulter. Les applets de commande de messagerie instantanée et présence aident si vous avez besoin plus de références.
  
## <a name="federation-policy"></a>Stratégie de fédération
<a name="FederationPolicy"> </a>

L’exemple de script pour la fédération est FederationPolicy.ps1. Les applets de commande pour passer en revue, si vous avez besoin d’un aperçu, sera serveur de périphérie, fédération et accès externe.
  
## <a name="call-admission-control-policy"></a>Politique de contrôle d’admission des appels
<a name="CACPolicy"> </a>

Vous pouvez référencer BandwidthPolicy.ps1 pour cette stratégie. Les applets de commande Call Admission Control aura plus ainsi que des informations.
  
## <a name="voice-routing-rules"></a>Règles de routage voix
<a name="VoiceRoutingRules"> </a>

Vous aurez besoin de l’exemple de script RoutingRules.ps1 pour le routage des communications vocales. Lorsque vous configurez ces règles, prenez note du contexte téléphonique (autrement dit, /Location profil ou /SimpleName) et les Codes de zone interne/externe, afin que vous pouvez spécifier les lors de la création d’utilisateurs. Vous aurez également besoin lors de la configuration LyncPerfTool (spécifiquement pour les UC-PSTN et UC-PSTN).
  
Par exemple, le paramètre SimpleName dans l’appel vers la cmdlet **New-CsDialPlan** dans l’exemple RoutingRules.ps1 doit être utilisé pour la valeur LocationProfile dans la figure suivante de UserProfileGenerator.exe :
  
![Chargez l’outil de configuration Skype Entreprise, onglet Scénarios vocaux, paramètres avancés de conversation.](../../media/59f42e4e-8f1e-4d43-9ae2-9e6026191951.png)
  
Pour plus d’informations, vous pouvez consulter les applets de commande voix entreprise.
  
## <a name="conference-attendant-application"></a>Application intendant Conférence
<a name="ConfAttendantApp"> </a>

Consultez tout d’abord le script ConferenceAutoAttendantConfiguration.ps1. Vous souhaiterez Notez le numéro de téléphone ConferencingAutoAttendant (1121111111 par défaut), afin que vous pouvez entrer dans l’outil de configuration LyncPerfTool pour la génération de configuration, comme indiqué ci-dessous :
  
![Onglet Scénarios vocaux affichant le niveau de charge de la conférence et le numéro de téléphone.](../../media/a3ea5fc0-8b3d-4842-b809-f137f470dbdc.png)
  
Vous trouverez plus de détails de la conférence et la conférence rendez-vous applets de commande.
  
## <a name="server-call-park-service"></a>Service de parcage d’appel de serveur
<a name="ServerCallParkServ"> </a>

En fait, il est désactivé par défaut. Vous pouvez consulter l’exemple de script CallParkConfiguration.ps1 si vous avez besoin effectuer ce test. En outre, consultez la rubrique les applets de commande d’Application de parcage d’appel selon vos besoins.
  
## <a name="emergency-calls"></a>Appels d’urgence
<a name="EmergencyCalls"> </a>

Vous devez effectuer les étapes suivantes pour configurer le contrainte et test de performances pour les appels d’urgence :
  
1. Configurer un itinéraire de communications vocales pour les appels d’urgence. Vous pouvez utiliser le script RoutingRules.ps1 et vérifiez sous le commentaire « **Itinéraire E911 PSTN** » pour obtenir un exemple de la façon de configurer cet itinéraire.
    
    > [!CAUTION]
    > L’exemple de commande dans RoutingRules.ps1 a un modèle de numéro qui inclut le nombre 119 plutôt que 911. Évitez d’utiliser 911 (ou votre numéro d’urgence local réel) pour empêcher les appels accidentelles à vos opérateurs d’urgence locales durant le test de charge. N’oubliez pas, cette configuration est uniquement à des fins de simulation ! 
  
2. Configurer des adresses en renseignant les valeurs sous l’onglet **Configuration du Service Info emplacement** dans la UserProvisioningTool, comme illustré dans la figure suivante :
    
     ![Outil d’affectation d’utilisateurs affichant le nombre d’adresses, de sous-réseaux, de commutateurs et de ports.](../../media/ebe85a0c-750f-4301-97d4-d158a40ea98a.png)
  
3. Lorsque vous avez entré tout dans la UserProvisioningTool, cliquez sur le bouton **Générer des fichiers de configuration LIS** .
    
4. Maintenant les fichiers CSV pour les ports, les sous-réseaux, les commutateurs et les points d’accès sans fil (WAP), ainsi que d’un fichier XML pour l’outil de Stress and Performance sera générée. Vous pouvez utiliser les fichiers CSV pour les entrées lors de la configuration du service informations d’emplacement (LIS) avec le script LisConfiguration.ps1. Pour ce faire, vous devez déplacer le fichier Locations0.xml vers le même dossier que le Stress and Performance Tool exécutable (LyncPerfTool.exe). Cela vous permettent d’exécuter des scénarios de (plan de numérotation) de profil d’emplacement.
    
## <a name="configuring-response-group-application"></a>Application de configuration Response Group
<a name="ConfigResponseGroupApp"> </a>

L’exemple de script est ResponseGroupConfiguration.ps1. Il existe également des cmdlets pour passer en revue pour plus d’informations de configuration de l’application Response Group. Le diagramme suivant affiche des informations de configuration :
  
![Outil de configuration de groupe de réponse affichant les flux de travail existants pour les tests.](../../media/e218a345-4813-4332-8cff-b48de05017ef.jpg)
  

