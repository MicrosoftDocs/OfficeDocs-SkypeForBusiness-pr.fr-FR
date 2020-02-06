---
title: Définition de l’interface utilisateur pour l’achat manuel d’un emplacement dans Skype entreprise Server
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
ms.assetid: d37f67d3-e248-483b-b64c-3986559ef357
description: Planification de l’itinérance des utilisateurs dans un déploiement E9-1-1 à l’aide de fournisseurs de trunking SIP dans Skype entreprise Server Voice.
ms.openlocfilehash: 85bf13325d3c7c16958877d50f49057a7f402226
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802714"
---
# <a name="define-the-user-experience-for-manually-acquiring-a-location-in-skype-for-business-server"></a>Définition de l’interface utilisateur pour l’achat manuel d’un emplacement dans Skype entreprise Server
 
Planification de l’itinérance des utilisateurs dans un déploiement E9-1-1 à l’aide de fournisseurs de trunking SIP dans Skype entreprise Server Voice.
  
Si un client se trouve à l’extérieur du réseau ou dans un sous-réseau non défini, l’utilisateur peut entrer manuellement un emplacement. Mais pendant un appel d’urgence, l’appel sera tout d’abord acheminé vers un répartiteur de centre de réponse aux appels d’urgence (Emergency Call Response Center, ou ECRC) E9-1-1 national ou régional avant d’être acheminé vers un centre téléphonique de sécurité publique (Public Safety Answering Point, ou PSAP). L’ECRC demande verbalement un emplacement à l’appelant, puis transfère l’appel au PSAP approprié en fonction des informations renseignées. 
  
**Les utilisateurs doivent-ils être invités à entrer un emplacement lorsque le service d’information d’emplacement n’est pas fourni automatiquement ?**
  
Par exemple, si un client se trouve dans un sous-réseau non défini, au domicile de l’utilisateur, dans un hôtel ou ailleurs à l’extérieur du réseau, l’utilisateur doit-il entrer un emplacement ?
    
Vous pouvez configurer le paramètre **Emplacement requis** dans la stratégie d’emplacement pour définir le comportement du client. Si vous lui attribuez la valeur Non, l’utilisateur ne sera pas invité à entrer un emplacement. Si vous lui attribuez la valeur Oui, l’utilisateur sera invité à entrer un emplacement, mais pourra ignorer le message d’invite. Si vous lui attribuez la valeur Clause d’exclusion de responsabilité, l’utilisateur sera invité à entrer un emplacement, et une notification d’exclusion s’affichera s’il essaie d’ignorer le message d’invite. Dans tous les cas, l’utilisateur peut continuer à utiliser le client comme d’habitude.
    
Lorsqu’un utilisateur entre manuellement à un emplacement, l’emplacement est mappé à l’adresse MAC de la passerelle par défaut du réseau du client et est stocké dans une table par utilisateur située sur le client. Lorsque l’utilisateur revient à un emplacement déjà stocké, le client Skype entreprise se positionne automatiquement à cet emplacement. 
  
> [!NOTE]
> Vous pouvez modifier uniquement l’emplacement actuel de votre client, mais vous pouvez également supprimer tout emplacement stocké dans la table de l’utilisateur local. 
  

