---
title: Modifications de schéma dans Skype pour Business Server
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
description: Avant de déployer et utiliser Skype pour Business Server, vous devez préparer les Services de domaine Active Directory en étendant le schéma. Les extensions de schéma ajoutent les classes et les attributs qui sont requis par Skype pour Business Server.
ms.openlocfilehash: 42b4417311c557323535aa03053ccb03d95cc840
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="schema-changes-in-skype-for-business-server"></a>Modifications de schéma dans Skype pour Business Server
 
Avant de déployer et utiliser Skype pour Business Server, vous devez préparer les Services de domaine Active Directory en étendant le schéma. Les extensions de schéma ajoutent les classes et les attributs qui sont requis par Skype pour Business Server. 
  
Skype pour Business Server requiert plusieurs nouvelles classes et attributs et modifie certaines classes existantes et les attributs. En outre, volume informations de configuration pour Skype pour Business Server sont stockées dans le magasin Central de gestion et non dans les services AD DS que dans les versions précédentes. Les informations suivantes sont toujours stockées dans AD DS dans Skype pour Business Server :
  
- **Extensions de schéma**:
    
  - Extensions de l’objet utilisateur
    
  - Extensions pour les classes assurer la compatibilité descendante avec les versions précédentes prises en charge de Lync Server.
    
- **Données** (stockés dans Skype pour schéma étendu du serveur de l’entreprise et dans les classes de schéma existant) :
    
  - Utilisateur SIP identificateur URI (Uniform Resource) et autres paramètres de l’utilisateur
    
  - Objets de contact pour les applications comme groupe de réponse et intendant
    
  - Pointeur vers le magasin Central de gestion
    
  - Compte d’authentification de Kerberos (un objet ordinateur facultatif)
    
Cette rubrique décrit les modifications de schéma Active Directory requises par Skype pour Business Server. Il ne décrit pas les modifications de schéma qui ont été introduites par les versions précédentes d’Office Communications Server. Pour obtenir une liste de classes et de leurs descriptions, voir [classes de schéma et de descriptions dans Skype pour Business Server](schema-classes-and-descriptions.md). Pour obtenir une liste des attributs et leurs descriptions, voir [attributs de schéma et de descriptions dans Skype pour Business Server](schema-attributes-and-descriptions.md). Pour obtenir une liste des classes avec les attributs qu’ils peuvent contenir, voir [attributs de schéma par classe dans Skype pour Business Server](schema-attributes-by-class.md).
  
Le préfixe de msRTCSIP identifie les classes et les attributs qui sont spécifiques à Skype pour Business Server.
  
## <a name="new-active-directory-attributes"></a>Nouveaux attributs d’Active Directory

Le tableau suivant décrit les attributs Active Directory qui sont ajoutés par Skype pour Business Server.
  
**Attributs ajoutés par Skype pour Business Server**

|**Attribut**|**Description**|
|:-----|:-----|
|msExchUserHoldPolicies  <br/> |Cet attribut à valeurs multiples conserve les identificateurs pour contiennent les stratégies qui s’appliquent à l’utilisateur. Maintenez les stratégies de conserver des éléments de boîte aux lettres de l’utilisateur pendant toute la durée de la suspension. Cet attribut est partagé avec Exchange 2013.  <br/> |
|msRTCSIP-UserRoutingGroupId  <br/> |Il s’agit de l’ID de groupe de routage de SIP Enregistrent les utilisateurs dans le même groupe sur le même serveur frontal.  <br/> |
|msRTCSIP-MirrorBackEndServer  <br/> |Cet attribut est utilisé pour stocker la mise en miroir back-end SQL Server utilisé par le pool de Front-End.  <br/> |
   
## <a name="modified-active-directory-classes"></a>Classes de modification Active Directory

Le tableau suivant décrit les classes Active Directory qui sont modifiés par Skype pour Business Server.
  
**Classes modifiés par Skype pour Business Server**

|**Classe**|**Modifier**|**Classe ou un attribut**|
|:-----|:-----|:-----|
|Utilisateur  <br/> |ajouter : mayContain  <br/> ajouter : mayContain  <br/> |ProxyAddresses  <br/> msRTCSIP-UserRoutingGroupId  <br/> |
|Contact  <br/> |ajouter : mayContain  <br/> ajouter : mayContain  <br/> |ProxyAddresses  <br/> msRTCSIP-UserRoutingGroupId  <br/> |
|Destinataire du message  <br/> |ajouter : mayContain  <br/> |msExchUserHoldPolicies  <br/> |
|msRTCSIP-GlobalTopologySetting  <br/> |ajouter : mayContain  <br/> |msRTCSIP-MirrorBackEndServer  <br/> |
   

