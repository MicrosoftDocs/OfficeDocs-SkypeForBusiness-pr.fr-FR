---
title: Stratégie d’emplacement
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.NcsLocMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5530cf17-4520-40b5-ba70-c62692685048
description: Les stratégies d’emplacement déterminent si le service E9-1-1 (Enhanced 9-1-1) doit être activé et définissent son mode d’utilisation. Elles indiquent également la façon dont les informations d’emplacement sont traitées pour les utilisateurs et les contacts.
ms.openlocfilehash: fa1ca0907d3316066e2ca6e1fcf8a1d09a9c315a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="location-policy"></a>Stratégie d’emplacement
 
Les stratégies d’emplacement déterminent si le service E9-1-1 (Enhanced 9-1-1) doit être activé et définissent son mode d’utilisation. Elles indiquent également la façon dont les informations d’emplacement sont traitées pour les utilisateurs et les contacts. 
  
Les stratégies d’emplacement incluent la stratégie globale, ainsi, éventuellement, qu’une ou plusieurs stratégies de site et utilisateur :
  
- **Stratégie globale :** La stratégie globale est créée par défaut. Vous pouvez modifier la stratégie globale, mais vous ne pouvez pas le supprimer. Si vous essayez de supprimer la stratégie globale, tous les paramètres sont réinitialisés aux valeurs par défaut.
    
- **Site de stratégies (facultatifs) :** Vous pouvez créer des stratégies d’emplacement site un ou plusieurs, chacun d’eux s’applique à un site spécifique. Les stratégies de site remplacent la stratégie globale.
    
- **Des stratégies d’utilisateur (facultatifs) :** Vous pouvez créer des stratégies d’emplacement utilisateur un ou plusieurs, chacun d’eux s’applique à un utilisateur spécifique ou un groupe d’utilisateurs. Les stratégies utilisateur remplacent la stratégie globale et les stratégies de site.
    
> [!NOTE]
> Vous pouvez également attribuer des stratégies d’emplacement à des sites réseau, qui sont des groupes de sous-réseaux. Les stratégies d’emplacement attribuées aux sites réseau prévalent sur toutes les autres stratégies utilisateur. Pour plus d’informations sur l’affectation des stratégies d’emplacement pour les sites de réseau à l’aide des applets de commande, voir [Ajouter une stratégie d’emplacement pour un site de RESEAU dans Skype pour Business Server 2015](../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md). Pour plus d’informations sur l’utilisation de Skype pour Business Server du Panneau de configuration pour affecter une stratégie d’emplacement sur un site de réseau, consultez [Configuration des Sites de réseau](http://technet.microsoft.com/library/358aa08a-c5bc-45fc-8017-19e6202f88c5.aspx). 
  
La page **Stratégie d’emplacement** affiche la liste de toutes les stratégies d’emplacement définies pour votre organisation.
  
## <a name="tasks-you-can-perform"></a>Tâches que vous pouvez effectuer

Dans la page **Stratégie d’emplacement**, vous pouvez effectuer les tâches suivantes :
  
- Création d’une stratégie d’emplacement de site ou d’une stratégie d’emplacement utilisateur
    
- Modification de la stratégie globale, d’une stratégie de site ou d’une stratégie utilisateur existante
    
- Suppression d’une stratégie de site ou d’une stratégie utilisateur
    
## <a name="ui-reference"></a>Référence d’interface utilisateur

La liste ci-dessous décrit les commandes de la page.
  
- **Nouveau** Démarre une nouvelle stratégie d’emplacement de site ou emplacement utilisateur.
    
- **Modifier** Ouvre la stratégie de l’emplacement sélectionné pour le modifier, sélectionne toutes les stratégies d’emplacement dans la liste ou supprimer la stratégie du site sélectionné ou utilisateur.
    
    > [!NOTE]
    > Pour la stratégie globale, l’option **Supprimer** restaure les valeurs par défaut des paramètres.
  
- **Actualiser** Actualise la liste des stratégies d’emplacement.
    
La liste ci-dessous décrit les champs de la page.
  
- **Nom** Identifie l’emplacement de stratégie.
    
- **Champ d’application** Identifie l’étendue de la stratégie d’emplacement : global, site ou à l’utilisateur.
    
- **E9-1-1** Vérifiez si les utilisateurs affectés à cette stratégie d’emplacement sont activés pour E9-1-1.
    
- **Emplacement** Spécifie si les utilisateurs sont invités à entrer des informations d’emplacement lors de leur client inscrit avec Skype pour Business Server à un nouvel emplacement, et si elles voient une décharge de responsabilité si elles ignorer l’invite sans entrer les informations d’emplacement.
    
- **Utilisation de TLS** Spécifie l’utilisation du réseau (RTPC) public commuté qui est utilisée pour déterminer l’itinéraire de la voix utilisée pour acheminer les appels d’urgence à partir des clients à l’aide de ce profil.
    
- **Nombre de E9-1-1** Spécifie le numéro qui est composé pour accéder à des services d’urgence.
    
- **Masque de E9-1-1** Spécifie un utilisateur compose un numéro qui est ensuite converti dans le nombre d’accès à distance en cas d’urgence.
    
Pour plus d’informations sur les fonctionnalités de service d’urgence de Voix Entreprise de, consultez [vue d’ensemble de E9-1-1](http://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) dans la documentation de planification. Pour plus d’informations sur l’utilisation de stratégies d’emplacement, reportez-vous à la section [Configuration de la stratégie emplacement](http://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx) dans la documentation sur les opérations.
  

