---
title: Créer des stratégies de conférence dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 8c685326-8356-4075-bf95-32324b16ef81
description: 'Résumé : Découvrez comment créer des stratégies de conférence dans Skype Entreprise Server.'
ms.openlocfilehash: 56404f98389dbe2fca6a6022e7d6f175bcca030c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60828827"
---
# <a name="create-conferencing-policies-in-skype-for-business-server"></a>Créer des stratégies de conférence dans Skype Entreprise Server
 
**Résumé :** Découvrez comment créer des stratégies de conférence dans Skype Entreprise Server.
  
Vous pouvez créer des stratégies de conférence à l’Skype Entreprise Server du Panneau de Skype Entreprise Server Management Shell.
  
## <a name="create-conferencing-policies-by-using-skype-for-business-server-control-panel"></a>Créer des stratégies de conférence à l’aide Skype Entreprise Server panneau de bord

1. Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.
    
2. Ouvrez Skype Entreprise Server panneau de contrôle.
    
3. Dans la barre de navigation de gauche, **cliquez** sur Conférence, puis sur Stratégie **de conférence.**
    
4. Cliquez sur **Nouveau**, puis effectuez l’une des opérations suivantes :
    
   - Pour créer une stratégie au niveau de l’utilisateur, cliquez sur **Stratégie utilisateur**. Dans **Nouvelle stratégie de conférence**, dans **Nom**, tapez un nom descriptif pour la stratégie.
    
   - Pour créer une stratégie au niveau site, cliquez sur **Stratégie de site**. Dans la zone de recherche **Sélectionner un site**, tapez entièrement ou partiellement le nom du site pour lequel vous voulez créer une stratégie. Dans la liste des sites, cliquez sur le site voulu, puis sur **OK**.
    
     > [!NOTE]
     > Le nom du site devient le nom de la stratégie de conférence . il ne peut pas être modifié. 
  
5. Dans **Description**, tapez la description de la stratégie.
    
6. Sous **Stratégie de l’organisateur**, dans **Taille maximale de la réunion**, tapez le nombre maximal d’utilisateurs autorisés à participer à une réunion. Par défaut, la taille maximale de la réunion est définie sur 250.
    
7. Pour empêcher les utilisateurs d’inviter des utilisateurs anonymes aux réunions, désactivez la case à cocher **Autoriser les participants à inviter des utilisateurs anonymes**. Les utilisateurs anonymes sont des utilisateurs qui n’ont pas d’informations d’identification dans les services de domaine Active Directory de votre organisation et qui, par conséquent, ne sont pas authentifiés. Par défaut, les utilisateurs peuvent inviter des utilisateurs anonymes aux réunions.
    
8. Dans **Enregistrement**, effectuez l’une des opérations suivantes :
    
   - Pour interdire aux participants d’enregistrer les réunions, cliquez sur **Aucun**. Il s’agit du paramètre par défaut.
    
   - Pour autoriser les participants à enregistrer les réunions, cliquez sur **Activer l’enregistrement**.
    
9. Pour autoriser les participants externes à enregistrer les réunions, activez la case à cocher **Autoriser les participants fédérés et anonymes à enregistrer**. Par défaut, le système interdit aux participants externes d’enregistrer les réunions.
    
10. Dans **Audio/vidéo**, effectuez l’une des opérations suivantes :
    
    - Pour interdire l’utilisation de l’audio et de la vidéo, cliquez sur **Aucun**.
    
    - Pour autoriser l’utilisation de l’audio mais pas de la vidéo, cliquez sur **Activer Audio sur IP**.
    
    - Pour autoriser l’utilisation de l’audio et de la vidéo, cliquez sur **Activer l’audio/la vidéo IP**. Il s’agit du paramètre par défaut.
    
11. Si vous avez choisi d’autoriser l’utilisation de l’audio dans **Audio/vidéo**, procédez comme suit :
    
    - Pour empêcher les utilisateurs de rejoindre la réunion via un appel à distance, désactivez la case à cocher **Activer la conférence rendez-vous PSTN**. Par défaut, les utilisateurs peuvent accéder aux réunions par le biais du réseau téléphonique commuté (RTC).
    
    - Si vous autorisez les utilisateurs à accéder aux réunions à distance et que vous souhaitez autoriser les utilisateurs non authentifiés (anonymes) à rejoindre une réunion via un appel téléphonique sortant, activez la case à cocher **Autoriser l’accès sortant des participants anonymes**. Avec l’appel téléphonique sortant, le serveur de conférence appelle l’utilisateur et celui-ci répond au téléphone pour rejoindre la réunion. Par défaut, les utilisateurs anonymes ne peuvent pas rejoindre une réunion via un appel téléphonique sortant.
    
12. Si vous avez choisi d’autoriser l’utilisation de la vidéo dans **l’audio/vidéo,** cochez **Autoriser plusieurs flux vidéo.**
    
13. Dans **Collaboration de données**, effectuez l’une des opérations suivantes :
    
    - Pour empêcher la collaboration de données, cliquez sur **Aucun**.
    
    - Pour autoriser la collaboration de données, cliquez sur **Activer la collaboration de données**. Il s’agit du paramètre par défaut.
    
14. Si vous avez choisi d’autoriser la collaboration de données dans **Collaboration de données**, procédez comme suit :
    
    - Pour interdire les téléchargements externes, désactivez la case à cocher **Autoriser les participants fédérés et anonymes à télécharger du contenu**. Par défaut, les utilisateurs externes peuvent télécharger du contenu.
    
    - Pour interdire les transferts de fichiers, désactivez la case à cocher **Autoriser les participants à transférer des fichiers**. Par défaut, les utilisateurs peuvent transférer des fichiers.
    
    - Pour interdire l’utilisation des annotations, désactivez la case à cocher **Activer les annotations**. Pour utiliser des annotations dans des présentations PowerPoint partagées, clear the **Enable PowerPoint annotations**. Par défaut, les annotations sont autorisées.
    
    - Pour interdire l’utilisation des sondages, désactivez la case à cocher **Activer les sondages**. Par défaut, les sondages sont autorisés.
    
15. Dans **Partage d’application**, effectuez l’une des opérations suivantes :
    
    - Pour interdire l’utilisation du partage d’application, cliquez sur **Désactiver le partage d’application**.
    
    - Pour autoriser l’utilisation du partage d’application, cliquez sur **Activer le partage d’application**. Il s’agit du paramètre par défaut.
    
16. Si vous avez choisi d’autoriser le partage d’application dans **Partage d’application**, procédez comme suit :
    
    - Pour empêcher les participants à la réunion de prendre le contrôle du partage d’application, désactivez la case à cocher **Autoriser les participants à prendre le contrôle**. Par défaut, les participants peuvent prendre le contrôle du partage d’application.
    
    - Si vous avez choisi d’autoriser les participants à la réunion à prendre le contrôle du partage d’application, activez la case à cocher **Autoriser les participants fédérés et anonymes à prendre le contrôle** pour autoriser les utilisateurs externes à prendre le contrôle du partage d’application. Par défaut, les utilisateurs externes ne peuvent pas prendre le contrôle du partage d’application.
    
17. Sous **Stratégie du participant**, effectuez l’une des opérations suivantes :
    
    - Pour interdire le partage d’application et le partage du Bureau, cliquez sur **Désactiver le partage d’application et de Bureau**.
    
    - Pour autoriser le partage d’application mais pas le partage du Bureau, cliquez sur **Activer le partage d’application**.
    
    - Pour autoriser le partage d’application et le partage du Bureau, cliquez sur **Activer le partage d’application et de Bureau**. Il s’agit du paramètre par défaut.
    
18. Pour interdire les transferts de fichiers d’homologue à homologue, désactivez la case à cocher **Autoriser le transfert de fichiers entre homologues**. Par défaut, les transferts de fichiers d’homologue à homologue sont autorisés.
    
19. Pour autoriser l’enregistrement d’homologue à homologue, activez la case à cocher **Activer l’enregistrement entre homologues**. Par défaut, l’enregistrement d’homologue à homologue n’est pas autorisé.
    
20. Pour autoriser les participants à participer avec plusieurs flux vidéo, activez la case à cocher **Autoriser les participants à participer avec plusieurs flux vidéo**. Par défaut, les flux vidéo multiples sont autorisés.
    
21. Cliquez sur **Valider**.
    
## <a name="create-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Créer des stratégies de conférence à l’aide Skype Entreprise Server Management Shell

Pour créer des stratégies de conférence, utilisez l’cmdlet **New-CsConferencingPolicy.**
  
L’exemple suivant crée une stratégie de conférence avec l’identité SalesConferencingPolicy. Cette stratégie utilise toutes les valeurs par défaut pour une stratégie de conférence à l’exception d’une seule : MaxMeetingSize. Dans cet exemple, la taille maximale d’une réunion sera définie sur 50 au lieu de la valeur par défaut de 250 :
  
```PowerShell
New-CsConferencingPolicy -Identity SalesConferencingPolicy -MaxMeetingSize 50
```

Pour plus d’informations, y compris une description complète de la syntaxe et la liste des paramètres, voir [New-CsConferencingPolicy](/powershell/module/skype/new-csconferencingpolicy?view=skype-ps).
