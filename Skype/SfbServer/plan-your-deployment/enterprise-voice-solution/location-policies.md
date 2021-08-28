---
title: Planifier des stratégies d’emplacement pour Skype Entreprise Server
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
ms.assetid: da3cca7f-f6e5-4b6f-90a1-2008e3dd1ebd
description: Lisez cette rubrique pour découvrir comment planifier des stratégies d’emplacement pour un déploiement des services d’urgence améliorés (E9-1-1) dans Skype Entreprise Server Voix Entreprise.
ms.openlocfilehash: b250108fb20a9a1d75069b1036ab7c2fba332443
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58601409"
---
# <a name="plan-location-policies-for-skype-for-business-server"></a>Planifier des stratégies d’emplacement pour Skype Entreprise Server
 
Lisez cette rubrique pour découvrir comment planifier des stratégies d’emplacement pour un déploiement des services d’urgence améliorés (E9-1-1) dans Skype Entreprise Server Voix Entreprise. 
  
> [!NOTE]
> Skype Entreprise Server prend désormais en charge la configuration de plusieurs numéros d’urgence pour un client. Si vous souhaitez configurer plusieurs numéros d’urgence, vous devez suivre les informations de la zone Planifier plusieurs numéros d’urgence dans [Skype Entreprise Server](multiple-emergency-numbers.md) et configurer plusieurs numéros d’urgence dans [Skype Entreprise](../../deploy/deploy-enterprise-voice/configure-multiple-emergency-numbers.md). 
  
Vous créez des stratégies d’emplacement à l Skype Entreprise panneau de Skype Entreprise ou à l’aide de l’cmdlet [New-CsLocationPolicy.](/powershell/module/skype/new-cslocationpolicy?view=skype-ps) Pour plus d’informations, voir [Créer des stratégies d’emplacement dans Skype Entreprise Server](../../deploy/deploy-enterprise-voice/create-location-policies.md).
  
Chaque stratégie d’emplacement contient les informations suivantes :
  
 **Activer Enhanced 9-1-1**
  
Lorsque cette valeur est activée, le client est activé pour les services d’urgence améliorés (E9-1-1). Lorsqu’un client s’inscrit, il tente d’acquérir un emplacement auprès du service Informations d’emplacement et inclut les informations d’emplacement dans le cadre d’un appel d’urgence.
  
 **Emplacement**
  
Ce paramètre est utilisé uniquement lorsque **l’enable enhanced 9-1-1** est activé.
  
Vous pouvez configurer le paramètre **Emplacement** pour définir le comportement du client comme suit :
  
- Définir la valeur sur **Non** signifie que l’utilisateur ne sera pas invité à se rendre sur un emplacement.
    
- Si la valeur est **Oui,** l’utilisateur est invité à se rendre sur un emplacement, mais peut ignorer l’invite.
    
- La définition de la valeur sur **Disclaimer** signifie que l’utilisateur est invité à se rendre sur un emplacement et qu’une clause d’exclusion de responsabilité s’affiche s’il tente d’ignorer l’invite. Dans tous les cas, l’utilisateur peut continuer à utiliser le client.
    
> [!NOTE]
> Le texte de la clause d’exclusion de responsabilité n’apparaît pas si un utilisateur a entré manuellement un emplacement avant d’être activé pour E9-1-1. Les mises à jour du texte de la clause d’exclusion de responsabilité ne seront pas vues par les utilisateurs qui ont déjà vu la clause d’exclusion de responsabilité. 
  
 **Exclusion de responsabilité du service d’urgence amélioré**
  
Ce paramètre spécifie la clause d’exclusion de responsabilité que les utilisateurs voient s’ils rejettent l’invite pour un emplacement. Dans Skype Entreprise Server, vous pouvez utiliser la stratégie d’emplacement pour définir différentes clauses d’exclusion de responsabilité pour différents paramètres régionaux ou différents ensembles d’utilisateurs.
  
 **Chaîne de numérotation d’urgence (numéro E9-1-1)**
  
Cette chaîne de numérotation (moins le « + » de début, mais incluant toute normalisation effectuée par le plan de numérotation de l’utilisateur) signifie qu’un appel est un appel d’urgence. La **chaîne de numérotation d’urgence** amène le client à inclure les informations de localisation et de rappel avec l’appel.
  
> [!NOTE]
> Si votre organisation n’utilise pas de préfixe d’accès à une ligne externe, vous n’avez pas besoin de créer une règle de normalisation de plan de numérotation correspondante qui ajoute un « + » à la chaîne 911 avant d’envoyer l’appel au routage sortant sur un serveur exécutant Skype Entreprise Server ; Le « + » est automatiquement précédé par le client Skype Entreprise suite à la stratégie d’emplacement. Toutefois, si votre site utilise un préfixe d’accès externe, vous devez ajouter une règle de normalisation à la stratégie de plan de numérotation applicable qui exclut le préfixe d’accès externe et ajoute le « + ». Par exemple, si votre emplacement utilise un préfixe d’accès externe de 9 et qu’un utilisateur compose le 9 911 pour appeler d’urgence, le client utilisera sa stratégie de plan de numérotation pour le normaliser sur +911 avant que le numéro composé ne soit évalué par les itinéraires dans le profil d’emplacement de l’appelant. 
  
 **Masques de chaîne de numérotation d’urgence (masque de numérotation E9-1-1)**
  
Liste de chaînes de numérotation séparées par des points-virgules qui est traduite dans la chaîne de numérotation **d’urgence spécifiée.** Par exemple, vous pouvez ajouter 112, qui est le numéro de service d’urgence pour la plupart de l’Europe. Un utilisateur Skype Entreprise d’Europe peut ne pas savoir que le 911 est le numéro d’urgence américain, mais il peut composer le 112 et obtenir le même résultat. Comme pour la chaîne de numérotation d’urgence, n’incluez pas de « + » avant chaque numéro et, si vous utilisez des codes d’accès aux lignes externes, veillez à ce que la stratégie de plan de numérotation de l’utilisateur applique des règles de normalisation pour le chiffre du code d’accès.
  
 **Utilisation PSTN**
  
Nom de l’utilisation PSTN qui contient les chemins de routage qui déterminent la passerelle SIP, la passerelle PSTN ou la passerelle ELIN vers laquelle les appels d’urgence seront appelés.
  
> [!NOTE]
> Une seule utilisation peut être affectée à une stratégie d’emplacement. Cette utilisation PSTN remplace les utilisations PSTN affectées à la stratégie de voix de l’utilisateur, mais s’applique uniquement aux appels placés sur la chaîne de numérotation d’urgence ou sur l’un des masques de chaîne de numérotation d’urgence. 
  
 **URI de notification**
  
Spécifie une ou plusieurs UR SIP du personnel de sécurité qui reçoit une notification de messagerie instantanée lorsqu’un appel d’urgence est passé. Les groupes de distribution sont pris en charge.
  
 **URI de la conférence**
  
Spécifie un numéro SDN (direct à l’intérieur) (généralement un numéro de service de sécurité) qui doit être pris en compte lors d’un appel d’urgence. 
  
 **Mode conférence**
  
Spécifie si l’URI de conférence sera pris en compte dans l’appel d’urgence à l’aide d’une communication à sens seul ou double. 
  
 **Intervalle d’actualisation de l’emplacement**
  
Spécifie la durée (en heures) entre les demandes des clients pour une mise à jour d’emplacement à partir du service Informations d’emplacement. La valeur peut être définie sur n’importe quelle valeur entre 1 et 12. La valeur par défaut est 4.
