---
title: Modifications de schéma dans Skype pour Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
description: Avant de déployer et utiliser Skype pour Business Server, vous devez préparer les Services de domaine Active Directory en étendant le schéma. Les extensions de schéma ajoutent les classes et attributs requis par Skype pour Business Server.
ms.openlocfilehash: 5b6c3f036b1bc194331c721ea2d45564f0827d1c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924842"
---
# <a name="schema-changes-in-skype-for-business-server"></a>Modifications de schéma dans Skype pour Business Server
 
Avant de déployer et utiliser Skype pour Business Server, vous devez préparer les Services de domaine Active Directory en étendant le schéma. Les extensions de schéma ajoutent les classes et attributs requis par Skype pour Business Server.

> [!NOTE]
> Si vous mettez à niveau à partir de Lync Server 2013 Skype pour Business Server 2015, aucune modification de schéma n’apportées et par conséquent, cet article ne s’applique pas.
  
Skype pour Business Server requiert plusieurs nouvelles classes et attributs et modifie certains attributs et les classes existantes. En outre, bien informations de configuration de Skype pour Business Server sont stockées dans le magasin Central de gestion et non dans AD DS que dans les versions précédentes. Les informations suivantes sont toujours stockées dans AD DS dans Skype pour Business Server :
  
- **Extensions de schéma**:
    
  - Extensions de l’objet utilisateur
    
  - Extensions pour les classes maintenir la compatibilité descendante avec les versions précédentes pris en charge de Lync Server.
    
- **Données** (stocké dans Skype pour le schéma étendu Business Server et dans les classes de schéma existantes) :
    
  - Utilisateur SIP identificateur URI (Uniform Resource) et autres paramètres utilisateur
    
  - Objets contact pour les applications telles que le service Response Group et intendant Conférence
    
  - Un pointeur vers le magasin Central de gestion
    
  - Compte d’authentification Kerberos (un objet ordinateur facultatif)
    
Cette rubrique décrit les modifications de schéma Active Directory requises par Skype pour Business Server. Il ne décrit pas les modifications de schéma qui ont été introduites par les versions précédentes d’Office Communications Server. Pour obtenir la liste des classes et leurs descriptions, voir [classes de schéma et les descriptions de Skype pour Business Server](schema-classes-and-descriptions.md). Pour obtenir la liste des attributs et leurs descriptions, voir [attributs de schéma et les descriptions de Skype pour Business Server](schema-attributes-and-descriptions.md). Pour obtenir la liste des classes avec les attributs qu’ils peuvent contenir, voir [attributs de schéma par classe dans Skype pour Business Server](schema-attributes-by-class.md).
  
Le préfixe msRTCSIP identifie les classes et attributs spécifiques à Skype pour Business Server.
  
## <a name="new-active-directory-attributes"></a>Nouveaux attributs Active Directory

Le tableau suivant décrit les attributs Active Directory qui sont ajoutés par Skype pour Business Server.
  
**Attributs ajoutés par Skype pour Business Server**

|**Attribut**|**Description**|
|:-----|:-----|
|msExchUserHoldPolicies  <br/> |Cet attribut à valeurs multiples conserve les identificateurs pour contenir les stratégies qui s’appliquent à l’utilisateur. Maintenez les stratégies de conserver les éléments de boîte aux lettres de l’utilisateur pendant la durée de la suspension. Cet attribut est partagé avec Exchange 2013.  <br/> |
|msRTCSIP-UserRoutingGroupId  <br/> |Il s’agit de la SIP routage ID de groupe. Les utilisateurs dans le même groupe inscrira sur le même serveur frontal.  <br/> |
|msRTCSIP-MirrorBackEndServer  <br/> |Cet attribut est utilisé pour stocker la mise en miroir principal SQL Server utilisé par le pool frontal.  <br/> |
   
## <a name="modified-active-directory-classes"></a>Classes Active Directory modifiées

Le tableau suivant décrit les classes Active Directory qui sont modifiées par Skype pour Business Server.
  
**Classes modifiées par Skype pour Business Server**

|**Classe**|**Modification**|**Classe ou un attribut**|
|:-----|:-----|:-----|
|Utilisateur  <br/> |ajouter : mayContain  <br/> ajouter : mayContain  <br/> |ProxyAddresses  <br/> msRTCSIP-UserRoutingGroupId  <br/> |
|Contact  <br/> |ajouter : mayContain  <br/> ajouter : mayContain  <br/> |ProxyAddresses  <br/> msRTCSIP-UserRoutingGroupId  <br/> |
|Destinataire du message  <br/> |ajouter : mayContain  <br/> |msExchUserHoldPolicies  <br/> |
|msRTCSIP-GlobalTopologySetting  <br/> |ajouter : mayContain  <br/> |msRTCSIP-MirrorBackEndServer  <br/> |
   

