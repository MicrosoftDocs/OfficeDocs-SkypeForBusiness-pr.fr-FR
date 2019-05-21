---
title: Planifier des politiques d’emplacement pour Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
description: Pour plus d’informations sur la planification de stratégies de géolocalisation pour un déploiement Enhanced Emergency Services (E9-1-1) dans Skype entreprise Server, voir la rubrique voix.
ms.openlocfilehash: 8f21a5a0f54fbeaca4c46ed51bf4dafe4c2a3dcb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276753"
---
# <a name="plan-location-policies-for-skype-for-business-server"></a>Planifier des politiques d’emplacement pour Skype entreprise Server
 
Pour plus d’informations sur la planification de stratégies de géolocalisation pour un déploiement Enhanced Emergency Services (E9-1-1) dans Skype entreprise Server, voir la rubrique voix. 
  
> [!NOTE]
> Skype entreprise Server prend désormais en charge la configuration de plusieurs numéros d’urgence pour un client. Si vous voulez configurer plusieurs numéros d’urgence, vous devez suivre les informations de l’offre [plan pour plusieurs numéros d’urgence dans Skype entreprise Server](multiple-emergency-numbers.md) et [configurer plusieurs numéros d’urgence dans Skype entreprise](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md). 
  
Vous pouvez créer des stratégies d’emplacement à l’aide du panneau de configuration Skype pour les entreprises ou à l’aide de l’applet [de commande New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) . Pour plus d’informations, reportez-vous à la rubrique [création de stratégies d’emplacement dans Skype entreprise Server](../../deploy/deploy-enterprise-voice/create-location-policies.md).
  
Chaque stratégie d’emplacement renferme les informations suivantes :
  
 **Activation d'Enhanced 9-1-1**
  
Si cette valeur est activée, le client est activé pour les services d’urgence étendus (E9-1-1). Lors de l’inscription d’un client, ce dernier tente d’acquérir un emplacement auprès du service d’information d’emplacement et inclut les informations d’emplacement dans le cadre d’un appel d’urgence.
  
 **Emplacement**
  
Ce paramètre est utilisé uniquement lorsque l'**activation d'Enhanced 9-1-1** est activée. 
  
Vous pouvez configurer le paramètre **Emplacement** pour définir le comportement du client de la manière suivante :   
  
- Si vous sélectionnez **Non **, l’utilisateur ne sera pas invité à entrer un emplacement.
    
- Si vous sélectionnez **Oui **, l’utilisateur sera invité à entrer un emplacement, mais pourra ignorer le message d’invite.
    
- Si vous sélectionnez **Clause d’exclusion de responsabilité **, l’utilisateur sera invité à entrer un emplacement, et une notification d’exclusion s’affichera également s’il essaie d’ignorer le message d’invite. Dans tous les cas, l'utilisateur peut continuer d'utiliser le client.
    
> [!NOTE]
> Le texte de la clause d’exclusion de responsabilité ne s’affiche pas si un utilisateur a entré manuellement un emplacement avant d’avoir été activé pour E9-1-1. Les mises à jour apportées à ce texte ne s’afficheront pas pour les utilisateurs ayant déjà pris connaissance de la clause d’exclusion de responsabilité.  
  
 **Clause d’exclusion de responsabilité du service d’urgence**
  
Ce paramètre spécifie la clause d’exclusion de responsabilité qui s’affiche si les utilisateurs ignorent l’invite pour un emplacement. Dans Skype entreprise Server, vous pouvez utiliser la stratégie d’emplacement pour définir différentes exclusions de responsabilité pour différentes régions ou ensembles d’utilisateurs différents.
  
 **Chaîne de numérotation d’urgence (numéro E9-1-1)**
  
Cette chaîne de numérotation (moins le "+" au début, mais y compris la normalisation réalisée par le plan de numérotation de l’utilisateur) signifie qu’un appel est un appel d’urgence. La **chaîne de numérotation d’urgence** oblige le client à inclure dans l’appel les informations d’emplacement et de rappel.
  
> [!NOTE]
> Si votre organisation n’utilise pas un préfixe d’accès aux lignes externes, vous n’avez pas besoin de créer une règle de normalisation de plan de numérotation correspondante qui ajoute «+» à la chaîne 911 avant d’envoyer l’appel vers le routage sortant sur un serveur exécutant Skype entreprise Server. le "+" sera automatiquement ajouté par le client Skype entreprise en raison de la stratégie d’emplacement. Toutefois, si votre site utilise un préfixe d’accès externe, vous devez ajouter une règle de normalisation à la stratégie de plan de numérotation appropriée qui élimine le préfixe d’accès externe et ajoute le signe «+». Par exemple, si votre emplacement utilise un préfixe d’accès externe de 9 et qu’un utilisateur compose 9 911 pour passer un appel d’urgence, le client utilisera sa stratégie de plan de numérotation pour normaliser cette opération sur + 911 avant que le numéro composé soit évalué par les itinéraires dans le profil de l’appelant. 
  
 **Masques de chaîne de numérotation d’urgence (masque E9-1-1)**
  
Liste séparée par des virgules des chaînes de numérotation traduites dans la chaîne de numérotation de **secours**spécifiée. Par exemple, vous souhaiterez peut-être ajouter 112, qui est le numéro de service d’urgence pour la plupart des services d’Europe. Un utilisateur de Skype entreprise en Europe ne sait pas que 911 correspond au numéro d’urgence des États-Unis, mais il peut composer 112 et obtenir le même résultat. Comme pour la chaîne de numérotation d’urgence, n’incluez pas de "+" devant chaque numéro et, si vous utilisez des codes d’accès de ligne externe, assurez-vous que la stratégie de plan de numérotation de l’utilisateur dispose de règles de normalisation pour supprimer le code d’accès.
  
 **Utilisation PSTN**
  
Nom de l’utilisation PSTN qui contient les chemins de routage qui déterminent la jonction SIP, la passerelle PSTN ou la passerelle ELIN vers laquelle les appels seront acheminés.
  
> [!NOTE]
> Seule une utilisation peut être affectée à une stratégie d’emplacement. Cette utilisation PSTN remplace les utilisations RTC attribuées à la stratégie vocale de l’utilisateur, mais ne s’applique qu’aux appels passés à la chaîne de numérotation d’urgence ou à un des masques de chaînes de numérotation d’urgence. 
  
 **URI de notification**
  
Indique les URI SIP des membres du personnel de sécurité qui reçoivent une notification de messagerie instantanée en cas d’appel d’urgence. Les groupes de distribution sont pris en charge.
  
 **URI de la conférence**
  
Indique le numéro SDA (en général, numéro de service de sécurité) qui doit participer à la conférence en cas d’appel d’urgence.   
  
 **Mode Conférence**
  
Indique si l’URI de conférence participera à l’appel d’urgence via une communication unidirectionnelle ou bidirectionnelle.  
  
 **Intervalle d’actualisation d’emplacement**
  
Spécifie la durée (en heures) entre les demandes des clients pour une mise à jour de l’emplacement du service d’informations d’emplacement. La valeur peut être comprise entre 1 et 12. La valeur par défaut est 4.
  

