---
title: Conditions préalables à la sécurité et à la configuration Voix Entreprise dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
description: 'Résumé : Découvrez les conditions préalables de sécurité et de configuration requises pour Voix Entreprise dans Skype Entreprise Server.'
ms.openlocfilehash: 0f46de6fa8b8c2027a3828df67a0330212392e45
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58617020"
---
# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-skype-for-business-server"></a>Conditions préalables à la sécurité et à la configuration Voix Entreprise dans Skype Entreprise Server
 
**Résumé :** Découvrez les conditions préalables de sécurité et de configuration pour Voix Entreprise dans Skype Entreprise Server.
  
Avant de déployer Voix Entreprise, vérifiez que votre infrastructure répond aux conditions préalables suivantes en matière de sécurité, de configuration utilisateur et de matériel spécifique au scénario. 
  
## <a name="administrative-rights-and-certificate-infrastructure"></a>Droits d’administration et infrastructure de certificats

Avant de déployer, vérifiez ce qui suit :
  
- Les administrateurs déployant Voix Entreprise doivent être membres du groupe RTCUniversalServerAdmins.
    
- Les administrateurs doivent disposer des droits appropriés pour effectuer les tâches de configuration :
    
  - **CsVoiceAdministrator :** Ce rôle permet à l’administrateur d’effectuer des tâches de configuration vocale, de gérer les applications vocales et d’affecter des stratégies vocales aux utilisateurs finaux.
    
  - **CsUserAdministrator :** Ce rôle permet à l’administrateur de gérer les propriétés des utilisateurs, par exemple, pour activer Voix Entreprise pour un utilisateur. Ce rôle permet également à l’administrateur d’affecter des stratégies par utilisateur, à l’exception de la stratégie d’archivage, et de gérer les téléphones de partie commune et les périphériques analogues.
    
  - **CsAdministrator :** Ce rôle permet à l’utilisateur d’effectuer toutes les tâches des rôles CsVoiceAdministrator et CsUserAdministrator.
    
- L’infrastructure MKI (Managed Key Infrastructure) est déployée et configurée, à l’aide d’une infrastructure d’autorité de certification Microsoft ou tierce.
    
    > [!NOTE]
    > Pour plus d’informations sur les certificats requis dans Skype Entreprise Server, voir [Environmental requirements for Skype Entreprise Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or Server requirements for Skype Entreprise Server [2019](../../../SfBServer2019/plan/system-requirements.md). 
  
## <a name="user-configuration"></a>Configuration utilisateur

Si vous avez coqueté le serveur de médiation avec chaque pool frontal ou serveur Édition Standard pendant le déploiement frontal, les paramètres utilisateur nécessaires pour Voix Entreprise ont été configurés automatiquement lors de l’installation des fichiers pour ces rôles serveur.
  
Si vous procédez à un nouveau déploiement de la charge de travail de Voix Entreprise, avant de commencer le processus de déploiement, désignez un numéro de téléphone principal pour chaque utilisateur pour lequel vous envisagez d’activer Voix Entreprise. En tant qu’administrateur, vous devez vous assurer que ce numéro est unique. Avant l’implémentation, tous les numéros de téléphone principaux doivent être normalisés (correctement formatés) et copiés dans la propriété **URI** de ligne de chaque utilisateur à l’aide du Panneau de Skype Entreprise Server.
  
> [!NOTE]
> Pour obtenir des exemples de numéros de téléphone principaux requis pour Voix Entreprise déploiement, voir [exemples de règles de normalisation.](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md#BKMK_SampleNormalizationRules) 
  
## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a>Étapes suivantes : installer des fichiers ou configurer la connectivité PSTN

Après avoir vérifié les conditions préalables logicielles et environnementales pour Voix Entreprise vous pouvez :
  
- Installez le serveur de médiation, comme décrit dans Déployer un serveur de médiation dans le Générateur de topologies dans [Skype Entreprise Server,](deploy-a-mediation-server.md)mais uniquement si vous souhaitez déployer un serveur de médiation ou un pool autonome, car les serveurs de médiation sont installés dans le cadre du processus de déploiement du pool frontal ou du serveur Édition Standard lors de la c cocation.
    
- Vous pouvez également commencer à configurer les paramètres pour router les appels pour Voix Entreprise [utilisateurs,](configure-trunks.md)comme décrit dans La configuration des Skype Entreprise Server .
    

