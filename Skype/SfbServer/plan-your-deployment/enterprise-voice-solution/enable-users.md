---
title: Permettre aux utilisateurs de E9-1-1 dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
description: Décisions nécessaires pour la politique d’emplacement pour un déploiement E9-1-1 dans Skype entreprise Server Voice, y compris les utilisateurs à activer et à prendre en charge les utilisateurs itinérants.
ms.openlocfilehash: 717b127a94fbac966476c681cfb7f6e81d91bde9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802954"
---
# <a name="enable-users-for-e9-1-1-in-skype-for-business-server"></a>Permettre aux utilisateurs de E9-1-1 dans Skype entreprise Server
 
Décisions nécessaires pour la politique d’emplacement pour un déploiement E9-1-1 dans Skype entreprise Server Voice, y compris les utilisateurs à activer et à prendre en charge les utilisateurs itinérants.
  
Lors de l’enregistrement du client, Skype entreprise Server utilise une stratégie d’emplacement pour configurer les propriétés E9-1-1 pour les utilisateurs d’Enterprise Voice. Cette stratégie contient les paramètres qui déterminent la façon dont E9-1-1 est implémenté. Par exemple, la stratégie d’emplacement contient des informations telles que la chaîne de numérotation d’urgence, et si un utilisateur est tenu d’entrer manuellement un emplacement si le service d’information d’emplacement n’en a pas fourni automatiquement un. Pour obtenir une définition complète d’une stratégie d’emplacement, reportez-vous à la rubrique [planification de stratégies d’emplacement pour Skype entreprise Server](location-policies.md).
  
Skype entreprise Server peut affecter une stratégie d’emplacement aux clients en fonction du sous-réseau, ou à des utilisateurs basés sur une stratégie globale, par site ou par utilisateur. Pour vous aider à prendre une décision quant au mode d’activation des utilisateurs, commencez par répondre aux questions suivantes.
  
 **Envisagez-vous d’activer tous les utilisateurs ou de limiter la prise en charge à des zones géographiques spécifiques de l’entreprise ?**
  
> Vous pouvez affecter un emplacement à tous les utilisateurs de votre entreprise à l’aide d’une stratégie d’emplacement globale. En revanche, en attribuant une stratégie d’emplacement à un site réseau Skype entreprise Server, puis en ajoutant des sous-réseaux au site, vous pouvez limiter le support de E9-1-1 à des emplacements sélectionnés au sein de l’entreprise et spécifier le comportement de routage de E9-1-1 pour chaque site. 
    
 **Envisagez-vous d’activer des utilisateurs individuels par le biais d’une stratégie utilisateur ?**
  
> Vous pouvez affecter directement des stratégies d’emplacement à des utilisateurs ou des objets contact de téléphone de partie commune spécifiques si vous voulez personnaliser leur prise en charge du service E-9-1-1.
    
 **Quand des clients se trouvent en dehors du réseau ou se connectent à partir d’un sous-réseau non défini, doivent-ils bénéficier du service E9-1-1 ?**
  
> Si des utilisateurs se voient attribuer une stratégie d’emplacement globale, de site ou par utilisateur, ils peuvent être obligés d’entrer manuellement un emplacement dans le client si le client ne se trouve pas dans un sous-réseau défini ou s’il n’y a pas de localisation trouvée par le service d’informations d’emplacement. Pour plus d’informations, reportez-vous à [la rubrique définition de l’interface utilisateur pour l’achat manuel d’un emplacement dans Skype entreprise Server](manually-acquiring-a-location.md).
    

