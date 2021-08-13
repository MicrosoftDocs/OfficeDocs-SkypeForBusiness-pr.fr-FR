---
title: 'Teams cas De Contoso voix : files d’attente d’appels et de files d’attente automatiques'
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
description: 'Teams cas de voix pour une entreprise multinationale : des files d’attente de service automatique et des files d’attente d’appels'
appliesto:
- Microsoft Teams
ms.openlocfilehash: bf1d7a5457af0d7463207c0bdbc9d50433b3142e2f72e7efc7f8c89ade82bc93
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54296421"
---
# <a name="contoso-case-study-auto-attendants-and-call-queues"></a>Étude de cas Contoso : attendants automatiques et files d’attente d’appels

Contoso était familiarisé avec les attendants automatiques et les files d’attente d’appels à partir de leur déploiement Skype Entreprise local. Pour comprendre comment configurer les attendants automatiques cloud et les files d’attente d’appels, ils ont examiné le plan des Teams automatiques et des files [d’attente d’appels.](plan-auto-attendant-call-queue.md)

## <a name="requirements-depending-on-site-type"></a>Conditions requises en fonction du type de site

Selon le type de site, Contoso avait les besoins suivants :

- Type de site A : systèmes de téléphonie hérités traditionnels 

  Le type de site A est nécessaire pour conserver le même numéro de téléphone associé au numéro de téléphone que le numéro de téléphone de son personnel de réception. Les départements clés pour chacun de ces sites ont leurs propres files d’attente d’appels qui sont acheminées vers les membres de l’équipe. Il y avait un mélange de sites qui utilisaient des Système téléphonique routage direct et des Système téléphonique des plans d’appel.  

- Type de site B : Skype Entreprise Voix Entreprise 

  Le type de site B existait des files d’attente et des files d’attente automatiques qui devaient être migrées vers Teams. Contoso devait conserver les numéros de téléphone associés aux travailleurs automatiques. Contoso a déplacé la plupart de ces sites vers des Système téléphonique’offre d’appels. Toutefois, aux emplacements où les plans d’appel n’étaient pas disponibles, Contoso a déplacé ces sites vers une configuration de routage direct.  

- Type de site C : Skype Entreprise Voix Entreprise & système de téléphonie hérité traditionnel 

  Le type de site C existait des attendants automatiques résidant dans le système de téléphonie hérité traditionnel. Les décisions et configurations de ce site étaient identiques au type de site A.   

- Pour tous les types de sites, Contoso a posé les questions suivantes :

  - Q : Allons-nous utiliser des numéros nouveaux ou existants ? 
    R : Contoso a décidé d’utiliser des numéros de téléphone existants pour être affectés au compte de service du attendant automatique. 

  - Q : Quand le attendant automatique sera-t-il disponible pour accepter les appels entrants ? 
    R : Contoso a décidé de définir les heures d’ouverture et de recevoir les appels reçus après les heures d’ouverture vers un attendant automatique « après les heures de travail ».  

  - Q : Comment les appels sont-ils acheminés aux membres d’une file d’attente d’appels : employé de service, série ou round routage ? 
    R : Contoso a décidé d’utiliser le routage Attendant, 

  - Q : Comment allons-nous déterminer quand un utilisateur doit ou non se faire appeler ? 
    R : Contoso a décidé d’utiliser les options de traitement des appels pour déterminer si l’agent est disponible : routage en fonction de la présence. 


## <a name="configuration"></a>Configuration

Les étapes à suivre pour configurer un attendant automatique et une file d’attente d’appels incluent les étapes [suivantes décrites](manage-resource-accounts.md)dans la liste Gérer les comptes de ressources : 

1. Obtenez un numéro de service. 

2. Obtenez une licence gratuite Système téléphonique d’utilisateur virtuel ou une licence utilisateur Système téléphonique payant à utiliser avec le compte de ressource ou une licence Système téléphonique utilisateur.

3. Créez le compte de ressource. Un responsable automatique ou une file d’attente d’appels est requis pour avoir un compte de ressource associé. 

4. Attribuer la Système téléphonique ou une Système téléphonique - Licence utilisateur virtuel au compte de ressource. Pour plus d’informations, [voir Microsoft 365 Système téléphonique licence – Utilisateur virtuel.](./teams-add-on-licensing/virtual-user.md)

5. Affectez un numéro de téléphone de service au compte de ressource que vous avez affecté aux licences. 

6. Créer une file d Système téléphonique d’attente ou un attendant automatique 

7. Lier le compte de ressource à une file d’attente d’appels ou un attendant automatique. 


### <a name="sites-with-phone-system-with-direct-routing"></a>Sites avec Système téléphonique routage direct 

Contoso a dû configurer le numéro de téléphone fourni par l’opérateur local comme numéro de service dans Office 365. 

- Pour configurer un numéro de téléphone disponible via le routage direct, Contoso a suivi les instructions situées dans Gérer les [comptes de ressources.](manage-resource-accounts.md) Étant donné Office 365 des numéros de téléphone locaux, Contoso a utilisé PowerShell pour terminer l’installation.   

- Pour configurer le attendant automatique cloud, Contoso a suivi les étapes décrites dans [La configuration d’un attendant automatique cloud.](create-a-phone-system-auto-attendant.md) 

- Pour configurer une file d’attente d’appels cloud, Contoso a suivi les étapes décrites dans créer une file d’attente [d’appels cloud.](create-a-phone-system-call-queue.md)  


### <a name="sites-with-phone-system-with-calling-plan"></a>Sites avec des Système téléphonique forfait d’appels

Contoso a dû porter le numéro de téléphone utilisé pour Skype Entreprise Voix Entreprise les employés à Système téléphonique Office 365. Cela permettait d’attribuer le même numéro en tant que numéro de service à un employé de service automatique. 

- Pour transférer le numéro de téléphone, Contoso a suivi les instructions de transfert des numéros de téléphone vers [Teams](./phone-number-calling-plans/transfer-phone-numbers-to-teams.md) et a obtenu des instructions supplémentaires sur la gestion des numéros de téléphone [pour votre organisation.](./manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

- Pour configurer un attendant automatique cloud, Contoso a suivi les étapes décrites dans [La configuration d’un attendant automatique cloud.](create-a-phone-system-auto-attendant.md)

-  Pour configurer une file d’attente d’appels cloud, Contoso a suivi les étapes décrites dans créer une file d’attente [d’appels cloud.](create-a-phone-system-call-queue.md)  

