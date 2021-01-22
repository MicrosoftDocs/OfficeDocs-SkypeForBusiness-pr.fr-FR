---
title: Étude de cas Teams voix Contoso
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
description: Étude de cas Voix Teams pour une entreprise multinationale
appliesto:
- Microsoft Teams
ms.openlocfilehash: a6ee08fa7bdeb1ded6bda384115a08048021cb67
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918730"
---
# <a name="contoso-case-study-auto-attendants-and-call-queues"></a>Étude de cas Contoso : attendants automatiques et files d’attente d’appels

Contoso était familiarisé avec les attendants automatiques et les files d’attente d’appels à partir de leur déploiement Skype Entreprise local. Pour comprendre comment configurer les attendants automatiques cloud et les files d’attente d’appels, ils ont examiné le plan des files d’attente et des files d’attente [automatiques de Teams.](plan-auto-attendant-call-queue.md)

## <a name="requirements-depending-on-site-type"></a>Conditions requises en fonction du type de site

Selon le type de site, Contoso avait les besoins suivants :

- Type de site A : systèmes de téléphonie hérités traditionnels 

  Le type de site A est nécessaire pour conserver le même numéro de téléphone associé au numéro de téléphone que le numéro de téléphone de son personnel de réception. Les départements clés pour chacun de ces sites ont leurs propres files d’attente d’appels qui sont acheminées vers les membres de l’équipe. Il y avait un mélange de sites qui utilisaient Phone System avec routage direct et Phone System avec des plans d’appels.  

- Type de site B : skype entreprise Voix Entreprise 

  Le type de site B avait des files d’attente et des files d’attente automatiques existantes qui devaient être migrées vers Teams. Contoso devait conserver les numéros de téléphone associés aux travailleurs automatiques. Contoso a déplacé la plupart de ces sites vers Phone System avec des forfaits d’appels. Toutefois, aux emplacements où les plans d’appel n’étaient pas disponibles, Contoso a déplacé ces sites vers une configuration de routage direct.  

- Type de site C : Skype Voix Entreprise & système de téléphonie hérité traditionnel 

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

2. Obtenez un système téléphonique gratuit - licence Utilisateur virtuel ou licence Système téléphonique payant à utiliser avec le compte de ressource ou une licence Système téléphonique.

3. Créez le compte de ressource. Un responsable automatique ou une file d’attente d’appels est requis pour avoir un compte de ressource associé. 

4. Affecter le système téléphonique ou un système téléphonique - Licence utilisateur virtuel au compte de ressource. Pour plus d’informations, [voir Microsoft 365 Phone System – Licence utilisateur virtuel.](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/virtual-user)

5. Affectez un numéro de téléphone de service au compte de ressource que vous avez affecté aux licences. 

6. Créer une file d’attente ou un attendant automatique du système téléphonique 

7. Lier le compte de ressource à une file d’attente d’appels ou un attendant automatique. 


### <a name="sites-with-phone-system-with-direct-routing"></a>Sites avec système téléphonique avec routage direct 

Contoso a dû configurer le numéro de téléphone fourni par l’opérateur local comme numéro de service dans Office 365. 

- Pour configurer un numéro de téléphone disponible via le routage direct, Contoso a suivi les instructions situées dans Gérer les [comptes de ressources.](manage-resource-accounts.md) Étant donné qu’Office 365 n’a pas connaissance des numéros de téléphone locaux, Contoso a utilisé PowerShell pour terminer l’installation.   

- Pour configurer le attendant automatique cloud, Contoso a suivi les étapes décrites dans [La configuration d’un attendant automatique cloud.](create-a-phone-system-auto-attendant.md) 

- Pour configurer une file d’attente d’appels cloud, Contoso a suivi les étapes décrites dans créer une file d’attente [d’appels cloud.](create-a-phone-system-call-queue.md)  


### <a name="sites-with-phone-system-with-calling-plan"></a>Sites avec système téléphonique avec forfait d’appels

Contoso a dû porter le numéro de téléphone utilisé pour les Voix Entreprise automatiques Skype Entreprise vers Office 365 Phone System. Cela permettait d’attribuer le même numéro en tant que numéro de service à un employé de service automatique. 

- Pour transférer le numéro de téléphone, Contoso a suivi les instructions de transfert des numéros de téléphone vers [Teams](https://docs.microsoft.com/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) et a obtenu des instructions supplémentaires sur la gestion des numéros de téléphone [pour votre organisation.](https://docs.microsoft.com/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

- Pour configurer un attendant automatique cloud, Contoso a suivi les étapes décrites dans [La configuration d’un attendant automatique cloud.](create-a-phone-system-auto-attendant.md)

-  Pour configurer une file d’attente d’appels cloud, Contoso a suivi les étapes décrites dans créer une file d’attente [d’appels cloud.](create-a-phone-system-call-queue.md)  

 