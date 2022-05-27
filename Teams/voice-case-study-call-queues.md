---
title: 'Teams étude de cas contoso vocale : standards automatiques et files d’attente d’appels'
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: 'Teams étude de cas de voix pour une société multinationale : standards automatiques et files d’attente d’appels'
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6c0b6da7bf00fd4e62cf3e9b3b08074bf1b42788
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681715"
---
# <a name="contoso-case-study-auto-attendants-and-call-queues"></a>Étude de cas Contoso : Standards automatiques et files d’attente d’appels

Contoso connaissait les standards automatiques et les files d’attente d’appels à partir de leur déploiement Skype Entreprise local. Pour comprendre comment configurer des standards automatiques cloud et des files d’attente d’appels, ils ont examiné [plan pour Teams standards automatiques et files d’attente d’appels](plan-auto-attendant-call-queue.md).

## <a name="requirements-depending-on-site-type"></a>Exigences en fonction du type de site

Selon le type de site, Contoso avait les besoins suivants :

- Type de site A : systèmes de téléphonie hérités traditionnels 

  Type de site A nécessaire pour conserver le même numéro de téléphone associé à la réception que le numéro de leurs standards automatiques. Les services clés de chacun de ces sites auraient leurs propres files d’attente d’appels qui seraient acheminées vers les membres de l’équipe. Il y avait un mélange de sites qui utilisaient Système téléphonique avec routage direct et Système téléphonique avec les forfaits d’appels.  

- Type de site B : Skype Entreprise Voix Entreprise 

  Le type de site B avait des standards automatiques et des files d’attente d’appels existants qui devaient migrer vers Teams. Contoso devait conserver les numéros de téléphone associés aux standards automatiques. Contoso a déplacé la majorité de ces sites vers Système téléphonique avec des forfaits d’appels. Toutefois, dans les rares emplacements où les forfaits d’appels n’étaient pas disponibles, Contoso a déplacé ces sites vers une configuration de routage direct.  

- Type de site C : Skype Entreprise Voix Entreprise & système de téléphonie hérité traditionnel 

  Le type de site C avait des standards automatiques existants qui résidaient dans le système de téléphonie hérité traditionnel. Les décisions et les configurations pour ce site étaient identiques à celles du type de site A.   

- Pour tous les types de sites, Contoso a posé les questions suivantes :

  - Q : Utiliserons-nous des nombres nouveaux ou existants ? 
    R : Contoso a décidé d’utiliser des numéros de téléphone existants pour être affecté au compte de service du standard automatique. 

  - Q : Quand le standard automatique sera-t-il disponible pour accepter les appels entrants ? 
    R : Contoso a décidé de définir les heures d’ouverture et a reçu des appels après les heures de bureau redirigés vers un standard automatique « après les heures ».  

  - Q : Comment les appels seront-ils acheminés vers les membres d’une file d’attente d’appels : standard, série ou routage par tourniquet (round robin) ? 
    R : Contoso a décidé d’utiliser le routage attendant, 

  - Q : Comment déterminer quand un utilisateur doit ou non recevoir un appel ? 
    R : Contoso a décidé d’utiliser les options de gestion des appels pour déterminer si l’agent est disponible : routage basé sur la présence. 


## <a name="configuration"></a>Configuration

Les étapes de configuration d’un standard automatique et d’une file d’attente d’appels incluent les éléments suivants décrits dans [Gérer les comptes de ressources](manage-resource-accounts.md) : 

1. Obtenez un numéro de service. 

2. Obtenez un Système téléphonique gratuit : une licence d’utilisateur virtuel ou une licence Système téléphonique payante à utiliser avec le compte de ressource ou une licence Système téléphonique.

3. Créez le compte de ressource. Un standard automatique ou une file d’attente d’appels est nécessaire pour avoir un compte de ressource associé. 

4. Affectez la Système téléphonique ou une Système téléphonique - Licence d’utilisateur virtuel au compte de ressource. Pour plus d’informations, consultez [Microsoft 365 Système téléphonique – Licence d’utilisateur virtuel](./teams-add-on-licensing/virtual-user.md).

5. Attribuez un numéro de téléphone de service au compte de ressource à lequel vous avez attribué des licences. 

6. Créer une file d’attente d’appels Système téléphonique ou un standard automatique 

7. Liez le compte de ressource à une file d’attente d’appels ou à un standard automatique. 


### <a name="sites-with-phone-system-with-direct-routing"></a>Sites avec Système téléphonique avec routage direct 

Contoso a dû configurer le numéro de téléphone fourni par l’opérateur local comme numéro de service dans Office 365. 

- Pour configurer un numéro de téléphone disponible via le routage direct, Contoso a suivi les instructions fournies dans [Gérer les comptes de ressources](manage-resource-accounts.md). Étant donné que Office 365 ne connaît pas les numéros de téléphone locaux, Contoso a utilisé PowerShell pour terminer la configuration.   

- Pour configurer le standard automatique cloud, Contoso a suivi les étapes décrites dans [Configurer un standard automatique cloud](create-a-phone-system-auto-attendant.md). 

- Pour configurer une file d’attente d’appels cloud, Contoso a suivi les étapes décrites dans [Créer une file d’attente d’appels cloud](create-a-phone-system-call-queue.md).  


### <a name="sites-with-phone-system-with-calling-plan"></a>Sites avec Système téléphonique avec plan d’appel

Contoso a dû porter le numéro de téléphone utilisé pour Skype Entreprise Voix Entreprise standards automatiques à Système téléphonique Office 365. Cela a permis d’affecter le même nombre en tant que numéro de service pour une utilisation en tant que standard automatique. 

- Pour porter le numéro de téléphone, Contoso a suivi les instructions de [Transfert de numéros de téléphone à Teams](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md) et a obtenu des conseils supplémentaires sur [la gestion des numéros de téléphone pour votre organisation](./manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

- Pour configurer un standard automatique cloud, Contoso a suivi les étapes décrites dans [Configurer un standard automatique cloud](create-a-phone-system-auto-attendant.md).

-  Pour configurer une file d’attente d’appels cloud, Contoso a suivi les étapes décrites dans [Créer une file d’attente d’appels cloud](create-a-phone-system-call-queue.md).  

