---
title: Modifications de schéma dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
description: Avant de déployer et d’Skype Entreprise Server, vous devez préparer les services de domaine Active Directory en étendant le schéma. Les extensions de schéma ajoutent les classes et attributs requis par Skype Entreprise Server.
ms.openlocfilehash: 9f5a0f5e3b70925a39d94df9d3fec6728ef6429c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60829818"
---
# <a name="schema-changes-in-skype-for-business-server"></a>Modifications de schéma dans Skype Entreprise Server
 
Avant de déployer et d’Skype Entreprise Server, vous devez préparer les services de domaine Active Directory en étendant le schéma. Les extensions de schéma ajoutent les classes et attributs requis par Skype Entreprise Server.

> [!NOTE]
> Si vous êtes en cours de mise à niveau de Lync Server 2013 vers Skype Entreprise Server 2015, aucune modification de schéma n’est apportée et, par conséquent, cet article ne s’applique pas.
  
Skype Entreprise Server nécessite plusieurs nouvelles classes et attributs et modifie certaines classes et attributs existants. En outre, de nombreuses informations de configuration pour Skype Entreprise Server sont stockées dans le magasin central de gestion et non dans AD DS comme dans les versions précédentes. Les informations suivantes sont toujours stockées dans AD DS dans Skype Entreprise Server :
  
- **Extensions de schéma** :
    
  - Extensions de l’objet utilisateur
    
  - Extensions pour les classes afin de maintenir la compatibilité ascendante avec les versions précédentes de Lync Server.
    
- **Données** (stockées dans Skype Entreprise Server schéma étendu et dans des classes de schéma existantes) :
    
  - URI (Uniform Resource Identifier) SIP de l’utilisateur et autres paramètres utilisateur
    
  - Objets contact pour des applications telles que le service Response Group et l’Intendant Conférence
    
  - Pointeur vers le magasin central de gestion
    
  - Compte d’authentification Kerberos (un objet ordinateur facultatif)
    
Cette rubrique décrit les modifications de schéma Active Directory requises par Skype Entreprise Server. Il ne décrit pas les modifications de schéma introduites par les versions précédentes de Office Communications Server. Pour obtenir la liste des classes et leurs descriptions, voir classes de schéma [et descriptions dans Skype Entreprise Server](schema-classes-and-descriptions.md). Pour obtenir la liste des attributs et leurs descriptions, voir attributs de schéma et [descriptions dans Skype Entreprise Server](schema-attributes-and-descriptions.md). Pour obtenir la liste des classes avec les attributs qu’elles peuvent contenir, voir [Attributs](schema-attributes-by-class.md)de schéma par classe dans Skype Entreprise Server .
  
Le préfixe msRTCSIP identifie les classes et les attributs spécifiques aux Skype Entreprise Server.
  
## <a name="new-active-directory-attributes"></a>Nouveaux attributs Active Directory

Le tableau suivant décrit les attributs Active Directory ajoutés par Skype Entreprise Server.
  
**Attributs ajoutés par Skype Entreprise Server**

|**Attribut**|**Description**|
|:-----|:-----|
|msExchUserHoldPolicies  <br/> |Cet attribut à valeurs multiples contient les stratégies d’archive qui s’appliquent à l’utilisateur. Les stratégies d’archive conservent les éléments de boîte aux lettres de l’utilisateur pendant la durée de la suspension. Cet attribut est partagé avec Exchange 2013.  <br/> |
|msRTCSIP-UserRoutingGroupId  <br/> |Il s’agit de l’ID de groupe de groupe de routage SIP. Les utilisateurs du même groupe seront inscrits au même serveur frontal.  <br/> |
|msRTCSIP-MirrorBackEndServer  <br/> |Cet attribut est utilisé pour stocker le pool SQL Server miroir utilisé par le pool frontal.  <br/> |
   
## <a name="modified-active-directory-classes"></a>Classes Active Directory modifiées

Le tableau suivant décrit les classes Active Directory modifiées par Skype Entreprise Server.
  
**Classes modifiées par Skype Entreprise Server**

|**Classe**|**Remplacez**|**Classe ou attribut**|
|:-----|:-----|:-----|
|Utilisateur  <br/> |ajouté : mayContain  <br/> ajouté : mayContain  <br/> |ProxyAddresses  <br/> msRTCSIP-UserRoutingGroupId  <br/> |
|Contact  <br/> |ajouté : mayContain  <br/> ajouté : mayContain  <br/> |ProxyAddresses  <br/> msRTCSIP-UserRoutingGroupId  <br/> |
|Mail-Recipient  <br/> |add: mayContain  <br/> |msExchUserHoldPolicies  <br/> |
|msRTCSIP-GlobalTopologySetting  <br/> |ajouté : mayContain  <br/> |msRTCSIP-MirrorBackEndServer  <br/> |
   

