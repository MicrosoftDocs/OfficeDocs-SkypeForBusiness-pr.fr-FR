---
title: Définir l’expérience utilisateur pour l’acquisition manuelle d’un emplacement dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d37f67d3-e248-483b-b64c-3986559ef357
description: Planification des utilisateurs itinérants dans un déploiement E9-1-1 à l’aide de fournisseurs de trunking SIP, Skype Entreprise Server Voix Entreprise.
ms.openlocfilehash: 8ca43e8d81d16068806c3416687f73c090a3cbae
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58602379"
---
# <a name="define-the-user-experience-for-manually-acquiring-a-location-in-skype-for-business-server"></a>Définir l’expérience utilisateur pour l’acquisition manuelle d’un emplacement dans Skype Entreprise Server
 
Planification des utilisateurs itinérants dans un déploiement E9-1-1 à l’aide de fournisseurs de trunking SIP, Skype Entreprise Server Voix Entreprise.
  
Si un client se trouve en dehors du réseau ou dans un sous-réseau non définie, l’utilisateur peut entrer manuellement un emplacement. Toutefois, au cours d’un appel d’urgence, l’appel est d’abord acheminé vers un répartiteur de centre d’appels d’urgence (ECRC) E9-1-1 national/régional avant d’être acheminé vers un centre d’appels de sécurité publique (PSAP). La CERC interrogera verbalement l’appelant pour obtenir un emplacement, puis le fera suivre au PSAP approprié, en fonction des informations fournies. 
  
**Les utilisateurs doivent-ils être invités à entrer un emplacement lorsqu’un emplacement n’est pas automatiquement fourni par le service Informations d’emplacement ?**
  
Par exemple, si un client se trouve dans un sous-réseau non définie, à la maison, à l’hôtel ou n’importe où en dehors du réseau, l’utilisateur doit-il entrer un emplacement ?
    
Vous pouvez configurer le paramètre **Emplacement requis** dans la stratégie d’emplacement pour définir le comportement du client. La définition de cette valeur sur Non signifie que l’utilisateur ne sera pas invité à se rendre sur un emplacement. La définition de cette valeur sur Oui signifie que l’utilisateur est invité à se rendre sur un emplacement, mais peut ignorer l’invite. La définition de cette valeur sur Disclaimer signifie que l’utilisateur est invité à se rendre sur un emplacement et qu’une clause d’exclusion de responsabilité s’affiche s’il tente d’ignorer l’invite. Dans tous les cas, l’utilisateur peut continuer à utiliser le client comme d’habitude.
    
Lorsqu’un utilisateur entre manuellement un emplacement, il est mappé à l’adresse MAC de la passerelle par défaut du réseau du client et stocké dans une table par utilisateur située sur le client. Lorsque l’utilisateur retourne à un emplacement précédemment stocké, le client Skype Entreprise se définit automatiquement à cet emplacement. 
  
> [!NOTE]
> Vous pouvez modifier uniquement l’emplacement actuel de votre client, mais vous pouvez également supprimer n’importe quel emplacement stocké dans la table de l’utilisateur local. 
  

