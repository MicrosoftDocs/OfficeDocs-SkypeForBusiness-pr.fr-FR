---
title: Créer des administrateurs du Panneau de configuration Skype Entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainCreateCSCPAdmin
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3312926a-4671-4030-bb92-90ac24c778dd
ROBOTS: NOINDEX, NOFOLLOW
description: 'Pour accorder l’accès au serveur Skype entreprise, procédez comme suit:'
ms.openlocfilehash: 6a605f77c5f2b04804506592ab61c7988d68acfc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298168"
---
# <a name="create-skype-for-business-server-control-panel-administrators"></a>Créer des administrateurs du Panneau de configuration Skype Entreprise Server
 
Pour accorder l’accès au serveur Skype entreprise, procédez comme suit:
  
1. Ouvrez une session en tant que membre du groupe Administrateurs du domaine ou du groupe RTCUniversalServerAdmins.
    
2. Ouvrez **Utilisateurs et ordinateurs Active Directory**, développez votre domaine, cliquez avec le bouton droit sur le conteneur **Utilisateurs**, puis cliquez sur **Propriétés**.
    
3. Dans **Propriétés de CSAdministrator**, cliquez sur l’onglet **Membres**.
    
4. Sous l’onglet Membres, cliquez sur **Ajouter**. Dans **Sélectionner des utilisateurs, des contacts, des ordinateurs, des comptes de service ou des groupes**, recherchez **Entrez les noms des objets à sélectionner**. Tapez le ou les noms d’utilisateur ou de groupe à ajouter au groupe CSAdministrators. Cliquez sur **OK**.
    
5. Sous l’onglet Membre, confirmez que les utilisateurs ou les groupes que vous avez sélectionnés sont présents. Cliquez sur **OK**.
    
> [!TIP]
> Le panneau de configuration Skype entreprise Server est un outil de contrôle d’accès basé sur un rôle. L’appartenance au groupe CsAdministrator donne à un utilisateur qui utilise le panneau de configuration Skype entreprise Server le contrôle total pour toutes les fonctions de configuration disponibles. D’autres rôles conçus pour des fonctions spécifiques sont disponibles. Les utilisateurs n’ont pas besoin d’être activés pour Skype entreprise Server afin d’être membres des groupes de gestion. 
  
Les autres rôles sont les suivants:
  
- **CsArchiving:** Les membres de ce groupe peuvent exécuter toutes les fonctions d’archivage, telles que la configuration et la gestion du rôle serveur d’archivage.
    
- **CsHelpDesk :** les membres de ce groupe peuvent afficher la configuration et le déploiement, y compris les propriétés et stratégies d’utilisateurs. Ils peuvent également effectuer des tâches de dépannage spécifiques.
    
- **CsLocationAdministrator :** les membres de ce groupe disposent des droits d’utilisateur les moins élevés associés à la gestion du système Enhanced 9-1-1 (E9-1-1). Ils peuvent créer des identificateurs de réseau et des emplacements E9-1-1 et les associer dans le déploiement.
    
- **CsResponseGroupAdministrator :** les membres peuvent gérer et configurer le service Response Group.
    
- **CsServerAdministrator:** Les membres peuvent gérer, surveiller et dépanner tous les serveurs exécutant Skype entreprise Server.
    
- **CsUserAdministrator :** les membres de ce groupe peuvent gérer, activer et désactiver des utilisateurs et assigner des stratégies existantes aux utilisateurs.
    
- **CsViewOnlyAdministrator:** Les membres peuvent afficher le déploiement et la configuration des informations serveur. Cette appartenance permet à un membre de surveiller l’état des serveurs exécutant Skype entreprise Server.
    
- **CsVoiceAdministrator:** Les membres peuvent créer, configurer et gérer les paramètres relatifs à la voix dans Skype entreprise Server.
    
Pour garantir la sécurité et l’intégrité des contrôles d’accès basée sur les rôles, ajoutez des utilisateurs aux groupes qui déterminent le rôle que l’utilisateur effectue dans la gestion du déploiement de Skype entreprise Server.
  

