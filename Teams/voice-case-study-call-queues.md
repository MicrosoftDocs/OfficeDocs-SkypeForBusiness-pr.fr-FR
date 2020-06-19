---
title: Étude de cas de voix contoso teams
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
description: Étude de cas de voix dans teams pour les entreprises à plusieurs nationaux
appliesto:
- Microsoft Teams
ms.openlocfilehash: 780d812b4e6e56b28b867ace14dbf1d5f6170302
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786021"
---
# <a name="contoso-case-study-auto-attendants-and-call-queues"></a>Étude de cas contoso : standards automatiques et files d’attente d’appels

Contoso s’est familier des standards automatiques et des files d’attente de son déploiement Skype entreprise local. Pour savoir comment configurer les standards automatiques Cloud, ils ont examiné [ce que sont les standards automatiques Cloud ?](what-are-phone-system-auto-attendants.md) et [exemples petite entreprise-définir le didacticiel du standard automatique](tutorial-org-aa.yml). Pour en savoir plus sur les options disponibles pour la configuration de files d’attente d’appels, le réviseur de Contoso [a examiné une file d’attente d’appels Cloud](create-a-phone-system-call-queue.md).  

## <a name="requirements-depending-on-site-type"></a>Conditions requises en fonction du type de site

En fonction du type de site, Contoso a-il besoin des éléments suivants :

- Type de site A : systèmes de téléphonie traditionnels traditionnels 

  Site tapez A requis pour conserver le même numéro de téléphone associé à la réceptionniste en tant que numéro de ses standards automatiques. Les services clés de chacun de ces sites disposeront de leurs propres files d’attente d’appels routables aux membres de l’équipe. Un mélange de sites utilisait un système téléphonique avec un routage direct et un système téléphonique avec des plans d’appels.  

- Type de site B : Skype entreprise voix entreprise 

  Le type de site B avait déjà des standards automatiques et des files d’attente d’appels pour migrer vers Teams. Contoso a besoin de conserver les numéros de téléphone associés aux standards automatiques. Contoso a déplacé la majorité de ces sites vers un système téléphonique avec des plans d’appels. Néanmoins, dans les rares emplacements où les plans d’appel ne sont pas disponibles, Contoso a déplacé ces sites vers une configuration de routage directe.  

- Type de site C : voix entreprise Skype entreprise & système de téléphonie traditionnel traditionnel 

  Le type de site C avait déjà des standards automatiques qui résident dans le système de téléphonie classique. Les décisions et configurations pour ce site étaient les mêmes que le type de site A.   

- Pour tous les types de sites, Contoso a posé les questions suivantes :

  - Q : utiliserez-vous des numéros nouveaux ou existants ? 
    A : contoso a décidé d’utiliser des numéros de téléphone existants à attribuer au compte de service pour le standard automatique. 

  - Q : quand le standard automatique sera-t-il disponible pour accepter les appels entrants ? 
    A : contoso a décidé de définir les heures d’activité et d’avoir reçu des appels lorsque les heures d’activité sont redirigées vers un standard automatique « après heures ».  

  - Q : comment les appels sont-ils acheminés vers les membres d’une file d’attente d’appels : le standard, le routage de série ou le routage par répétition alternée ? 
    A : contoso a décidé d’utiliser le service de routage de l’assistance. 

  - Q : Comment puis-je déterminer à quel moment un utilisateur doit ou ne doit pas être appelé ? 
    A : contoso a décidé d’utiliser les options de traitement des appels pour déterminer si l’agent est disponible : routage basé sur la présence. 


## <a name="configuration"></a>Configuration

Pour configurer un standard automatique et une file d’attente d’appels, vous pouvez suivre les étapes décrites dans [gérer les comptes de ressources](manage-resource-accounts.md): 

1. Obtenez un numéro de service. 

2. Procurez-vous un système téléphonique gratuit ou une licence de système téléphonique payant à utiliser avec le compte de ressources ou une licence de système téléphonique.

3. Créez le compte de ressource. Un standard automatique ou une file d’attente d’appels doivent être associés à un compte de ressources associé. 

4. Attribuez le système téléphonique ou un système téléphonique-licence utilisateur virtuel au compte de ressources. Pour plus d’informations, reportez-vous à [la rubrique système téléphonique Microsoft 365-licence utilisateur virtuel](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/virtual-user).

5. Affectez un numéro de téléphone de service au compte de ressources auquel vous avez attribué des licences. 

6. Créer une file d’attente des appels du système téléphonique ou un standard automatique 

7. Liez le compte de ressource avec une file d’attente d’appels ou un standard automatique. 


### <a name="sites-with-phone-system-with-direct-routing"></a>Sites avec système téléphonique avec routage direct 

Contoso a créé le numéro de téléphone fourni par l’opérateur local en tant que numéro de service dans Office 365. 

- Pour configurer un numéro de téléphone disponible via le routage direct, Contoso a suivi les instructions situées dans [gérer les comptes de ressources](manage-resource-accounts.md). Comme Office 365 ne connaît pas les numéros de téléphone locaux, Contoso a utilisé PowerShell pour terminer la configuration.   

- Pour configurer le standard automatique du Cloud, Contoso a suivi les étapes décrites dans l’article [configurer un standard automatique Cloud](create-a-phone-system-auto-attendant.md). 

- Pour configurer une file d’attente d’appels Cloud, Contoso a suivi les étapes décrites dans la rubrique [créer une file d’attente d’appels Cloud](create-a-phone-system-call-queue.md).  


### <a name="sites-with-phone-system-with-calling-plan"></a>Sites avec système téléphonique avec un plan d’appels

Contoso a dû porter le numéro de téléphone utilisé pour les standards automatiques vocaux Skype entreprise vers un système téléphonique Office 365. Le même numéro a été attribué en tant que numéro de service à utiliser comme standard automatique. 

- Pour porter le numéro de téléphone, Contoso a suivi les instructions contenues dans les sections [transférer les numéros de téléphone aux équipes](https://docs.microsoft.com/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) et obtenu des conseils supplémentaires sur [la gestion des numéros de téléphone pour votre organisation](https://docs.microsoft.com/microsoftteams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization).

- Pour configurer un standard automatique Cloud, Contoso a suivi les étapes décrites dans l’article [configurer un standard automatique Cloud](create-a-phone-system-auto-attendant.md).

-  Pour configurer une file d’attente d’appels Cloud, Contoso a suivi les étapes décrites dans la rubrique [créer une file d’attente d’appels Cloud](create-a-phone-system-call-queue.md).  

 