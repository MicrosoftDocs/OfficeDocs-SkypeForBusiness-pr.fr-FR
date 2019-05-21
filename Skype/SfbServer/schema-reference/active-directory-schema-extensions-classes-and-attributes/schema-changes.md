---
title: Modifications de schéma dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
description: Avant de déployer et d’utiliser Skype entreprise Server, vous devez préparer les services de domaine Active Directory en étendant le schéma. Les extensions de schéma ajoutent les classes et attributs requis par Skype entreprise Server.
ms.openlocfilehash: 34f97f7a37adc23635f938fb12c9a72e22429538
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296657"
---
# <a name="schema-changes-in-skype-for-business-server"></a>Modifications de schéma dans Skype entreprise Server
 
Avant de déployer et d’utiliser Skype entreprise Server, vous devez préparer les services de domaine Active Directory en étendant le schéma. Les extensions de schéma ajoutent les classes et attributs requis par Skype entreprise Server.

> [!NOTE]
> Si vous effectuez une mise à niveau de Lync Server 2013 vers Skype entreprise Server 2015, il n’y a aucune modification de schéma et c’est pourquoi cet article ne s’applique pas.
  
Skype entreprise Server nécessite plusieurs nouvelles classes et attributs, et modifie les classes et attributs existants. De plus, de nombreuses informations de configuration pour Skype entreprise Server sont stockées dans le magasin de gestion central plutôt que dans AD DS comme dans les versions précédentes. Les informations suivantes sont toujours stockées dans AD DS dans Skype entreprise Server:
  
- **Extensions de schéma**:
    
  - Extensions de l’objet utilisateur
    
  - Extensions de classes permettant de maintenir la compatibilité descendante avec les versions précédentes de Lync Server prises en charge.
    
- **Data (données** ) (stockés dans le schéma étendu de Skype entreprise Server et dans les classes de schéma existantes):
    
  - URL (Uniform Resource Identifier) de l’utilisateur SIP et autres paramètres utilisateur
    
  - Objets de contact pour des applications telles que Response Group et attendant
    
  - Pointeur vers le magasin de gestion central
    
  - Compte d’authentification Kerberos (objet facultatif de l’ordinateur)
    
Cette rubrique décrit les modifications de schéma Active Directory requises par Skype entreprise Server. Elle ne décrit pas les modifications de schéma introduites par des versions antérieures d’Office Communications Server. Pour obtenir la liste des classes et leurs descriptions, voir [classes et descriptions de schéma dans Skype entreprise Server](schema-classes-and-descriptions.md). Pour obtenir la liste des attributs et leur description, voir [attributs et descriptions de schéma dans Skype entreprise Server](schema-attributes-and-descriptions.md). Pour obtenir la liste des classes avec les attributs qu’ils peuvent contenir, voir [attributs de schéma par classe dans Skype entreprise Server](schema-attributes-by-class.md).
  
Le préfixe msRTCSIP identifie les classes et attributs spécifiques à Skype entreprise Server.
  
## <a name="new-active-directory-attributes"></a>Nouveaux attributs Active Directory

Le tableau suivant décrit les attributs Active Directory ajoutés par Skype entreprise Server.
  
**Attributs ajoutés par Skype entreprise Server**

|**Attribut**|**Description**|
|:-----|:-----|
|msExchUserHoldPolicies  <br/> |Cet attribut à plusieurs valeurs contient des identificateurs pour les stratégies de conservation qui s’appliquent à l’utilisateur. Les stratégies de blocage préservent les éléments de boîte aux lettres de l’utilisateur pendant la durée de la conservation. Cet attribut est partagé avec Exchange 2013.  <br/> |
|msRTCSIP-UserRoutingGroupId  <br/> |Il s’agit de l’ID du groupe de routage SIP. Les utilisateurs du même groupe seront enregistrés sur le même serveur principal.  <br/> |
|msRTCSIP-MirrorBackEndServer  <br/> |Cet attribut est utilisé pour stocker le serveur principal SQL Server utilisé par le pool frontal.  <br/> |
   
## <a name="modified-active-directory-classes"></a>Classes Active Directory modifiées

Le tableau suivant décrit les classes Active Directory modifiées par Skype entreprise Server.
  
**Classes modifiées par Skype entreprise Server**

|**Cours**|**Modification**|**Classe ou attribut**|
|:-----|:-----|:-----|
|Utilisateur  <br/> |Ajouter: mayContain  <br/> Ajouter: mayContain  <br/> |ProxyAddresses  <br/> msRTCSIP-UserRoutingGroupId  <br/> |
|Locuteur  <br/> |Ajouter: mayContain  <br/> Ajouter: mayContain  <br/> |ProxyAddresses  <br/> msRTCSIP-UserRoutingGroupId  <br/> |
|Mail-destinataire  <br/> |Ajouter: mayContain  <br/> |msExchUserHoldPolicies  <br/> |
|msRTCSIP-GlobalTopologySetting  <br/> |Ajouter: mayContain  <br/> |msRTCSIP-MirrorBackEndServer  <br/> |
   

