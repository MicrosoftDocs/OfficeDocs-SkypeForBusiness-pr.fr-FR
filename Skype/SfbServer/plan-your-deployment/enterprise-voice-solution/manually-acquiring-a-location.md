---
title: Définir l’expérience utilisateur pour acquérir manuellement un emplacement dans Skype pour Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d37f67d3-e248-483b-b64c-3986559ef357
description: Planification pour des utilisateurs itinérants dans un déploiement E9-1-1 à l’aide de fournisseurs d’acheminement SIP dans Skype pour Business Server Enterprise Voice.
ms.openlocfilehash: 921724b2dc93b852cebe6a34acbd8d4d66a594f8
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23881810"
---
# <a name="define-the-user-experience-for-manually-acquiring-a-location-in-skype-for-business-server"></a>Définir l’expérience utilisateur pour acquérir manuellement un emplacement dans Skype pour Business Server
 
Planification pour des utilisateurs itinérants dans un déploiement E9-1-1 à l’aide de fournisseurs d’acheminement SIP dans Skype pour Business Server Enterprise Voice.
  
Si un client se trouve à l’extérieur du réseau ou dans un sous-réseau non défini, l’utilisateur peut entrer manuellement un emplacement. Mais pendant un appel d’urgence, l’appel sera tout d’abord acheminé vers un répartiteur de centre de réponse aux appels d’urgence (Emergency Call Response Center, ou ECRC) E9-1-1 national ou régional avant d’être acheminé vers un centre téléphonique de sécurité publique (Public Safety Answering Point, ou PSAP). L’ECRC demande verbalement un emplacement à l’appelant, puis transfère l’appel au PSAP approprié en fonction des informations renseignées. 
  
**Les utilisateurs doivent être invités à entrer un emplacement lorsqu’elle n’est pas automatiquement fournie par le service informations d’emplacement ?**
  
Par exemple, si un client se trouve dans un sous-réseau non défini, au domicile de l’utilisateur, dans un hôtel ou ailleurs à l’extérieur du réseau, l’utilisateur doit-il entrer un emplacement ?
    
Vous pouvez configurer le paramètre **Emplacement requis** dans la stratégie d’emplacement pour définir le comportement du client. Si vous lui attribuez la valeur Non, l’utilisateur ne sera pas invité à entrer un emplacement. Si vous lui attribuez la valeur Oui, l’utilisateur sera invité à entrer un emplacement, mais pourra ignorer le message d’invite. Si vous lui attribuez la valeur Clause d’exclusion de responsabilité, l’utilisateur sera invité à entrer un emplacement, et une notification d’exclusion s’affichera s’il essaie d’ignorer le message d’invite. Dans tous les cas, l’utilisateur peut continuer à utiliser le client comme d’habitude.
    
Lorsqu’un utilisateur entre manuellement un emplacement, l’emplacement est mappé à l’adresse MAC de la passerelle par défaut du réseau du client et est stocké dans une table par utilisateur située sur le client. Lorsque l’utilisateur revient à n’importe quel emplacement stocké précédemment, la Skype pour client Business lui-même définit automatiquement à cet emplacement. 
  
> [!NOTE]
> Vous pouvez modifier uniquement l’emplacement actuel de votre client, mais vous pouvez également supprimer les emplacements stockés dans la table de l’utilisateur local. 
  

