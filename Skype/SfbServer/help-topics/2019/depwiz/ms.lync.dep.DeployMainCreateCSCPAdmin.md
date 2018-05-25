---
title: Créer des administrateurs du Panneau de configuration Skype Entreprise Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainCreateCSCPAdmin
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3312926a-4671-4030-bb92-90ac24c778dd
description: 'Pour accorder l’accès à la Skype pour Business Server 2015, procédez comme suit :'
ms.openlocfilehash: db781611e2df2abf23c071673d3dfe0570f5700b
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/24/2018
---
# <a name="create-skype-for-business-server-control-panel-administrators"></a>Créer des administrateurs du Panneau de configuration Skype Entreprise Server
 
Pour accorder l’accès à la Skype pour Business Server 2015, procédez comme suit :
  
1. Ouvrez une session en tant que membre du groupe Administrateurs du domaine ou du groupe RTCUniversalServerAdmins.
    
2. Ouvrez **Utilisateurs et ordinateurs Active Directory**, développez votre domaine, cliquez avec le bouton droit sur le conteneur **Utilisateurs**, puis cliquez sur **Propriétés**.
    
3. Dans **Propriétés de CSAdministrator**, cliquez sur l’onglet **Membres**.
    
4. Sous l’onglet Membres, cliquez sur **Ajouter**. Dans **Sélectionner des utilisateurs, des contacts, des ordinateurs, des comptes de service ou des groupes**, recherchez **Entrez les noms des objets à sélectionner**. Tapez le ou les noms d’utilisateur ou de groupe à ajouter au groupe CSAdministrators. Cliquez sur **OK**.
    
5. Sous l’onglet Membre, confirmez que les utilisateurs ou les groupes que vous avez sélectionnés sont présents. Cliquez sur **OK**.
    
> [!TIP]
> Le Skype pour Business Server Control Panel est un outil de contrôle d’accès basé sur un rôle. L’appartenance au groupe CsAdministrator donne à un utilisateur qui utilise le Skype pour contrôle total Business Server Control Panel pour toutes les fonctions de configuration disponibles. Il existe d’autres rôles disponibles conçus pour des fonctions spécifiques. Utilisateurs n’ont pas être activé pour Skype pour Business Server afin de devenir membres des groupes d’administration. 
  
Autres rôles sont les suivantes :
  
- **CsArchiving :** Membres de ce groupe peuvent effectuer toutes les fonctions d’archivage, comme la configuration et la gestion du rôle de serveur d’archivage.
    
- **CsHelpDesk :** les membres de ce groupe peuvent afficher la configuration et le déploiement, y compris les propriétés et stratégies d’utilisateurs. Ils peuvent également effectuer des tâches de dépannage spécifiques.
    
- **CsLocationAdministrator :** les membres de ce groupe disposent des droits d’utilisateur les moins élevés associés à la gestion du système Enhanced 9-1-1 (E9-1-1). Ils peuvent créer des identificateurs de réseau et des emplacements E9-1-1 et les associer dans le déploiement.
    
- **CsResponseGroupAdministrator :** les membres peuvent gérer et configurer le service Response Group.
    
- **CsServerAdministrator :** Les membres peuvent gérer, surveiller et dépanner tous les serveurs exécutant Skype pour Business Server.
    
- **CsUserAdministrator :** les membres de ce groupe peuvent gérer, activer et désactiver des utilisateurs et assigner des stratégies existantes aux utilisateurs.
    
- **CsViewOnlyAdministrator :** Les membres peuvent afficher le déploiement et la configuration des informations de serveur. Cet abonnement permet à un membre afin de surveiller l’intégrité des serveurs exécutant Skype pour Business Server 2015.
    
- **CsVoiceAdministrator :** Les membres peuvent créer, configurer et gérer les paramètres de voix dans Skype pour Business Server.
    
Pour préserver la sécurité et l’intégrité de contrôle d’accès basé sur un rôle, ajouter des utilisateurs aux groupes qui définissent le rôle tenu par l’utilisateur dans la gestion de la Skype pour le déploiement de serveur d’entreprise.
  

