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
description: 'Pour accorder l’accès à la Skype pour Business Server 2015, effectuez les opérations suivantes :'
ms.openlocfilehash: db781611e2df2abf23c071673d3dfe0570f5700b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="create-skype-for-business-server-control-panel-administrators"></a>Créer des administrateurs du Panneau de configuration Skype Entreprise Server
 
Pour accorder l’accès à la Skype pour Business Server 2015, effectuez les opérations suivantes :
  
1. Ouvrez une session en tant que membre du groupe Administrateurs du domaine ou du groupe RTCUniversalServerAdmins.
    
2. Ouvrez **Utilisateurs et ordinateurs Active Directory**, développez votre domaine, cliquez avec le bouton droit sur le conteneur **Utilisateurs**, puis cliquez sur **Propriétés**.
    
3. Dans **Propriétés de CSAdministrator**, cliquez sur l’onglet **Membres**.
    
4. Sous l’onglet Membres, cliquez sur **Ajouter**. Dans **Sélectionner des utilisateurs, des contacts, des ordinateurs, des comptes de service ou des groupes**, recherchez **Entrez les noms des objets à sélectionner**. Tapez le ou les noms d’utilisateur ou de groupe à ajouter au groupe CSAdministrators. Cliquez sur **OK**.
    
5. Sous l’onglet Membre, confirmez que les utilisateurs ou les groupes que vous avez sélectionnés sont présents. Cliquez sur **OK**.
    
> [!TIP]
> Le Skype pour le panneau de configuration de Business Server est un outil de contrôle d’accès basé sur les rôles. Appartenance au groupe CsAdministrator donne à l’utilisateur qui utilise le Skype pour le panneau de configuration de Business Server un contrôle total sur toutes les fonctions de configuration disponibles. Il existe d’autres rôles disponibles conçus pour des fonctions spécifiques. Les utilisateurs n’ont pas à activer pour Skype pour Business Server afin de devenir membres des groupes d’administration. 
  
Autres rôles sont les suivants :
  
- **CsArchiving :** Les membres de ce groupe peuvent effectuer toutes les fonctions d’archivage, tels que la configuration et la gestion du rôle de serveur d’archivage.
    
- **CsHelpDesk :** les membres de ce groupe peuvent afficher la configuration et le déploiement, y compris les propriétés et stratégies d’utilisateurs. Ils peuvent également effectuer des tâches de dépannage spécifiques.
    
- **CsLocationAdministrator :** les membres de ce groupe disposent des droits d’utilisateur les moins élevés associés à la gestion du système Enhanced 9-1-1 (E9-1-1). Ils peuvent créer des identificateurs de réseau et des emplacements E9-1-1 et les associer dans le déploiement.
    
- **CsResponseGroupAdministrator :** les membres peuvent gérer et configurer le service Response Group.
    
- **CsServerAdministrator :** Les membres peuvent gérer, contrôler et résoudre les problèmes de tous les serveurs exécutant Skype pour Business Server.
    
- **CsUserAdministrator :** les membres de ce groupe peuvent gérer, activer et désactiver des utilisateurs et assigner des stratégies existantes aux utilisateurs.
    
- **CsViewOnlyAdministrator :** Les membres peuvent afficher le déploiement et la configuration des informations serveur. Cet abonnement permet à un membre surveiller la santé des serveurs Skype pour Business Server 2015.
    
- **CsVoiceAdministrator :** Les membres peuvent créer, configurer et gérer les paramètres liés à la voix dans Skype pour Business Server.
    
Pour vous aider à assurer la sécurité et intégrité de contrôle d’accès basé sur des rôles, ajouter des utilisateurs aux groupes qui définissent quel rôle de l’utilisateur dans la gestion de la Skype pour le déploiement du serveur de l’entreprise.
  

