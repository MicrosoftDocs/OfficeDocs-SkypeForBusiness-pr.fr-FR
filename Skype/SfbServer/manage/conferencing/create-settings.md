---
title: Créer des paramètres de configuration de réunion dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6d8f9ff8-2a04-4175-9bf0-1ec5d78fd015
description: 'Résumé : Découvrez comment créer des paramètres de configuration de réunion dans Skype Entreprise Server.'
ms.openlocfilehash: ad1f4fabf172fa5ff693a91e7994916487c322e7
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58595566"
---
# <a name="create-meeting-configuration-settings-in-skype-for-business-server"></a>Créer des paramètres de configuration de réunion dans Skype Entreprise Server
 
**Résumé :** Découvrez comment créer des paramètres de configuration de réunion dans Skype Entreprise Server.
  
Vous pouvez créer des paramètres de configuration de réunion à l’Skype Entreprise Server du Panneau de configuration ou Skype Entreprise Server Management Shell.
  
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Créer des paramètres de configuration de réunion à l’aide Skype Entreprise Server panneau de configuration

1. Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.
    
2.  Ouvrez Skype Entreprise Server panneau de contrôle.
    
3. Dans la barre de navigation de gauche, cliquez sur **Conférence,** puis sur **Configuration de la réunion.**
    
4. Dans la page **Configuration de la réunion**, cliquez sur **Nouveau**, puis effectuez l’une des opérations suivantes :
    
    - Pour créer une stratégie au niveau du site, cliquez sur **Configuration du site**. Dans le champ de recherche **Sélectionner un site**, tapez le nom du site (en totalité ou partiellement) pour lequel vous souhaitez définir des paramètres de participation aux réunions. Dans la liste des sites obtenus, cliquez sur le site voulu, puis sur **OK**.
    
    - Pour créer une stratégie au niveau du pool, cliquez sur **Configuration du pool**. Dans le champ de recherche **Sélectionner un service**, tapez le nom du service de pool (en totalité ou partiellement) pour lequel vous souhaitez définir des paramètres de participation aux réunions. Dans la liste des services obtenus, cliquez sur le pool de votre choix, puis sur **OK**.
    
5. Pour acheminer les participants qui appellent depuis le réseau téléphonique commuté (RTC) via la salle d’attente, désactivez la case à cocher **Les appelants PSTN ignorent la salle d’attente**. Par défaut, les participants qui appellent depuis un réseau RTC accèdent directement à la réunion.
    
6. Pour désigner le présentateur de la réunion, dans **Désigné comme présentateur**, effectuez l’une des opérations suivantes :
    
   - Pour n’autoriser que l’organisateur à être présentateur, cliquez sur **Aucun**.
    
   - Pour n’autoriser que les participants membres de votre entreprise à être présentateur, cliquez sur **Société**. Il s’agit du paramètre par défaut.
    
   - Pour autoriser tous les participants à être présentateur, cliquez sur **Tout le monde**.
    
7. Pour permettre à l’organisateur de sélectionner un type de conférence lors de la planification d’une réunion, désactivez la case à cocher **Type de conférence affecté par défaut**. Par défaut, le type de conférence est automatiquement affecté.
    
8. Pour empêcher les utilisateurs anonymes (non identifiés) d’être automatiquement admis, désactivez la case à cocher **Admettre les utilisateurs anonymes par défaut**. Par défaut, les utilisateurs anonymes sont automatiquement admis aux réunions.
    
9. Pour personnaliser l’invitation à la réunion envoyée aux participants, procédez comme suit. Notez que la longueur maximale des URL et du texte de pied de page personnalisé est de 1 Ko. Sauf pour l’**URL de l’aide**, si vous ne spécifiez pas une valeur pour les personnalisations, elles ne seront pas incluses dans la réunion. Si vous n’incluez pas d’URL d’aide personnalisée, l’URL d’aide par Skype Entreprise’aide par défaut s’affiche dans l’invitation. 
    
   - Pour personnaliser le logo qui apparaît dans l’invitation à la réunion, dans **URL du logo**, entrez l’emplacement du logo. Le logo doit être une image GIF ou JPG d’une taille de 188 par 30 pixels. 
    
   - Pour personnaliser le texte d’aide qui apparaît dans l’invitation à la réunion, dans **URL de l’aide**, entrez l’emplacement du texte d’aide.
    
   - Pour personnaliser les informations légales qui apparaissent dans l’invitation à la réunion, dans **URL des informations légales**, entrez l’emplacement des informations légales.
    
   - Pour personnaliser le texte de pied de page qui apparaît dans l’invitation à la réunion, dans **Texte de pied de page personnalisé**, entrez le texte.
    
10. Cliquez sur **Valider**.
    
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>Créer des paramètres de configuration de réunion à l’aide Skype Entreprise Server Management Shell

Pour créer des paramètres de configuration de réunion, utilisez l’cmdlet **New-CsMeetingConfiguration.**
  
La commande suivante crée un nouvel ensemble de paramètres de configuration de réunion pour le site Redmond :
  
```PowerShell
New-CsMeetingConfiguration -Identity "site:Redmond"
```

Comme aucun paramètre (autre que le paramètre d’identité obligatoire) n’est spécifié dans la commande précédente, les nouveaux paramètres de configuration de réunion utiliseront les valeurs par défaut pour toutes ses propriétés.
  
Pour créer des paramètres qui utilisent différentes valeurs de propriété, incluez simplement le paramètre et la valeur de paramètre appropriés. Par exemple, pour créer une collection de paramètres de configuration de réunion qui, par défaut, admet tout le monde à une réunion comme présentateur, utilisez une commande semblable à la suivante :
  
```PowerShell
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

Plusieurs valeurs de propriété peuvent être définies en incluant plusieurs paramètres. Par exemple, la commande suivante admet tout le monde à une réunion en tant que présentateur et force également les utilisateurs PSTN à attendre dans la salle d’attente jusqu’à ce qu’ils soient officiellement admis à la réunion :
  
```PowerShell
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True
```

Pour plus d’informations, y compris une liste complète des paramètres, voir [New-CsMeetingConfiguration](/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps).
