---
title: Définition de l’expérience utilisateur pour l’acquisition manuelle d’un emplacement dans Skype Entreprise Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: d37f67d3-e248-483b-b64c-3986559ef357
description: Planification des utilisateurs itinérants dans un déploiement E9-1-1 à l’aide de fournisseurs de trunking SIP dans Skype pour Business Server Voix Entreprise.
ms.openlocfilehash: 6a22883fb5f028288ab3fab0246d6c2b3b693987
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="define-the-user-experience-for-manually-acquiring-a-location-in-skype-for-business-server-2015"></a>Définition de l’expérience utilisateur pour l’acquisition manuelle d’un emplacement dans Skype Entreprise Server 2015
 
Planification des utilisateurs itinérants dans un déploiement E9-1-1 à l’aide de fournisseurs de trunking SIP dans Skype pour Business Server Voix Entreprise.
  
Si un client se trouve à l’extérieur du réseau ou dans un sous-réseau non défini, l’utilisateur peut entrer manuellement un emplacement. Mais pendant un appel d’urgence, l’appel sera tout d’abord acheminé vers un répartiteur de centre de réponse aux appels d’urgence (Emergency Call Response Center, ou ECRC) E9-1-1 national ou régional avant d’être acheminé vers un centre téléphonique de sécurité publique (Public Safety Answering Point, ou PSAP). L’ECRC demande verbalement un emplacement à l’appelant, puis transfère l’appel au PSAP approprié en fonction des informations renseignées. 
  
**Doivent les utilisateurs invités à entrer un emplacement lorsqu’une n’est pas fournie automatiquement par le service d’informations d’emplacement ?**
  
Par exemple, si un client se trouve dans un sous-réseau non défini, au domicile de l’utilisateur, dans un hôtel ou ailleurs à l’extérieur du réseau, l’utilisateur doit-il entrer un emplacement ?
    
Vous pouvez configurer le paramètre **Emplacement requis** dans la stratégie d’emplacement pour définir le comportement du client. Si vous lui attribuez la valeur Non, l’utilisateur ne sera pas invité à entrer un emplacement. Si vous lui attribuez la valeur Oui, l’utilisateur sera invité à entrer un emplacement, mais pourra ignorer le message d’invite. Si vous lui attribuez la valeur Clause d’exclusion de responsabilité, l’utilisateur sera invité à entrer un emplacement, et une notification d’exclusion s’affichera s’il essaie d’ignorer le message d’invite. Dans tous les cas, l’utilisateur peut continuer à utiliser le client comme d’habitude.
    
Lorsqu’un utilisateur entre manuellement un emplacement, l’emplacement est mappé à l’adresse MAC de la passerelle par défaut du réseau du client et est stocké dans une table d’utilisateur située sur le client. Lorsque l’utilisateur revient à n’importe quel emplacement préalablement stockée, la Skype pour client d’entreprise lui-même définit automatiquement à cet emplacement. 
  
> [!NOTE]
> Vous pouvez modifier uniquement l’emplacement actuel de votre client, mais vous pouvez également supprimer n’importe quel emplacement stocké dans la table de l’utilisateur local. 
  

