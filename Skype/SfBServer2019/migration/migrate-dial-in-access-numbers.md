---
title: Migrer les numéros d’accès entrant
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: La migration des numéros d’accès rendez-vous dans Skype entreprise Server 2019 nécessite l’exécution de l’applet de connexion Move-CsApplicationEndpoint pour migrer les objets de contact. Lors de l’installation héritée et de la période de coexistence 2019 de Skype entreprise Server, les numéros d’accès rendez-vous créés dans Skype entreprise Server 2019 se comportent de la même manière que les numéros d’accès entrants que vous créez dans l’installation héritée, comme décrit dans cet zone.
ms.openlocfilehash: 81f100979d009f4f9b48cf9a538ec92095a67ad8
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36238045"
---
# <a name="migrate-dial-in-access-numbers"></a>Migrer les numéros d’accès entrant

La migration des numéros d’accès rendez-vous dans Skype entreprise Server 2019 nécessite l’exécution de l’applet de connexion **Move-CsApplicationEndpoint** pour migrer les objets de contact. Lors de l’installation héritée et de la période de coexistence 2019 de Skype entreprise Server, les numéros d’accès rendez-vous créés dans Skype entreprise Server 2019 se comportent de la même manière que les numéros d’accès entrants que vous créez dans l’installation héritée, comme décrit dans cet zone. 

Les numéros d’accès rendez-vous créés lors de l’installation de Skype entreprise Server 2019 ou que vous avez créés dans Skype entreprise Server 2019 avant, pendant ou après la migration, présentent les caractéristiques suivantes:

- N’apparaissent pas dans les invitations aux réunions Office Communications Server 2007 R2 et la page numéro d’accès rendez-vous.

- Apparaissent sur les invitations à la réunion d’installation héritée et sur la page numéro d’accès rendez-vous.

- S’affichent dans les invitations aux réunions 2019 de Skype entreprise Server et la page des numéros d’accès rendez-vous.

- Ne peut pas être affiché ou modifié dans l’outil d’administration d’Office Communications Server 2007 R2.

- Peut être affiché et modifié dans le panneau de configuration de l’installation légué et dans l’environnement d’administration de l’installation héritée.

- Peut être affiché et modifié dans le panneau de configuration Skype entreprise Server 2019 et dans Skype entreprise Server 2019 Management Shell.

- Peuvent être réécrits au sein de la région à l’aide de l’applet de requête Set-CsDialinConferencingAccessNumber avec le paramètre Priority.

Vous devez mettre fin à la migration des numéros d’accès rendez-vous qui pointent vers le pool d’installation hérité avant de désactiver le pool d’installation hérité. Si vous n’avez pas terminé la migration des numéros d’accès rendez-vous, comme indiqué dans la procédure suivante, les appels entrants vers les numéros d’accès échoueront.

> [!IMPORTANT]
> Vous devez effectuer cette procédure avant de désaffecter le pool d’installation hérité. 

> [!NOTE]
> Nous vous recommandons de déplacer les numéros d’accès rendez-vous lorsque le niveau d’utilisation du réseau est faible, en cas de panne de service de courte durée. 

## <a name="to-identify-and-move-dial-in-access-numbers"></a>Pour identifier et déplacer les numéros d’accès rendez-vous

1. Démarrez Skype entreprise Server Management Shell: cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Microsoft Skype entreprise Server 2019**, puis cliquez sur **Skype entreprise Server Management Shell**.

2. Pour déplacer chaque numéro d’accès entrant vers un pool hébergé sur Skype entreprise Server 2019, à partir de la ligne de commande exécutée: 

   ```
   Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>
   ```

3. Ouvrez le panneau de configuration Skype entreprise Server.

4. Dans la barre de navigation de gauche, cliquez sur **Conférences**.

5. Cliquez sur l’onglet **numéro d’accès** rendez-vous. 

6. Vérifiez qu’il n’y a pas de numéros d’accès rendez-vous pour le pool d’installation hérité à partir duquel vous effectuez la migration.

    > [!NOTE]
    > Lorsque tous les numéros d’accès entrant pointent vers le pool Skype entreprise Server 2019, vous pouvez désactiver le pool d’installation hérité. 

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-control-panel"></a>Vérifier la migration des numéros d’accès rendez-vous à l’aide du panneau de configuration Skype entreprise Server

1. À partir d’un compte d’utilisateur affecté au rôle **CsUserAdministrator** ou au rôle **CsAdministrator** , connectez-vous à n’importe quel ordinateur dans votre déploiement interne. 

2. Ouvrez le panneau de configuration Skype entreprise Server.

3. Dans la barre de navigation de gauche, cliquez sur **Conférences**.

4. Cliquez sur l’onglet **numéro d’accès** rendez-vous. 

5. Vérifiez que tous les numéros d’accès rendez-vous sont déplacés vers le pool hébergé sur Skype entreprise Server 2019.

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-management-shell"></a>Vérifier la migration des numéros d’accès entrants à l’aide de Skype entreprise Server Management Shell

1. Ouvrez Skype entreprise Server Management Shell.

2. Pour rétablir tous les numéros d’accès pour les conférences rendez-vous transférés, à partir de la ligne de commande:

   ```
   Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}
   ```

3. Vérifiez que tous les numéros d’accès rendez-vous sont déplacés vers le pool hébergé sur Skype entreprise Server 2019.


