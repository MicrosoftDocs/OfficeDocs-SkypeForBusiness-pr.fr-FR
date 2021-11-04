---
title: Affecter des stratégies de conférence pour prendre en charge les utilisateurs anonymes
ms.reviewer: ''
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48184333
mtps_version: v=OCS.15
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Pour déterminer quels sont les utilisateurs qui peuvent inviter des utilisateurs anonymes, vous devez configurer une stratégie de conférence pour la prise en charge des utilisateurs anonymes, et appliquer cette stratégie de conférence à des utilisateurs spécifiques.
ms.openlocfilehash: 8f4b62afb8a80e6dfa5a2c5be22ac70ea030ebb5
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60763742"
---
# <a name="assign-conferencing-policies-to-support-anonymous-users-in-skype-for-business-server"></a>Affecter des stratégies de conférence pour prendre en charge les utilisateurs anonymes dans Skype Entreprise Server 


Par défaut, aucun utilisateur ne peut inviter d’utilisateurs anonymes à participer à une réunion. Pour déterminer quels sont les utilisateurs qui peuvent inviter des utilisateurs anonymes, vous devez configurer une stratégie de conférence pour la prise en charge des utilisateurs anonymes, et appliquer cette stratégie de conférence à des utilisateurs spécifiques. Pour plus d’informations sur la configuration d’une stratégie de conférence pour prendre en charge les utilisateurs anonymes, voir Créer des stratégies de conférence dans [Skype Entreprise Server](../../conferencing/create-policies.md) et Gestion de la fédération et de l’accès externe [à Skype Entreprise Server](../managing-federation-and-external-access.md).

Suivez la procédure décrite dans cette section pour appliquer une stratégie de conférence, que vous avez déjà créée, à un ou plusieurs utilisateurs ou groupes d’utilisateurs.

> [!NOTE]  
> Outre la configuration et l’application d’une stratégie pour permettre aux utilisateurs d’inviter des utilisateurs anonymes, vous devez aussi activer la prise en charge des utilisateurs anonymes pour votre organisation. Pour plus d’informations, voir [Configurer des stratégies pour contrôler l’accès des](../external-access-policies/configure-policies-to-control-public-user-access.md)utilisateurs publics dans Skype Entreprise Server .


## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a>Pour configurer une stratégie utilisateur en vue d’une participation anonyme aux réunions

1.  Avec un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou d’un compte avec des droits d’utilisateur équivalents) ou assigné au rôle CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord. 

3.  Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis effectuez l’une des opérations suivantes :
    
    1.  Pour créer une nouvelle stratégie utilisateur, cliquez sur **Nouveau**, puis sur **Stratégie de l’utilisateur**. Dans le champ **Nom**, créez un nom unique indiquant ce qu’englobe la stratégie utilisateur (par exemple, **AutoriserAnonyme** pour une stratégie utilisateur qui autorise les communications avec des utilisateurs anonymes).
    
    2.  Pour configurer une stratégie utilisateur existante, cliquez sur la stratégie appropriée dans le tableau, cliquez sur **Modifier**, puis cliquez sur **Afficher les détails**.

4.  Dans la boîte de dialogue **Stratégies de conférence**, activez la case à cocher **Autoriser les participants à inviter des utilisateurs anonymes**.

5.  Cliquez sur **Valider**.

6.  Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**, puis recherchez le compte d’utilisateur que vous souhaitez configurer.

7.  Dans le tableau répertoriant les résultats de la recherche, cliquez sur le compte d’utilisateur, cliquez sur **Modifier**, puis cliquez sur **Afficher les détails**.

8.  Dans **Modifier Skype Entreprise Server utilisateur** sous Stratégie de conférence, sélectionnez la stratégie utilisateur avec la configuration d’accès utilisateur anonyme que vous souhaitez appliquer à cet utilisateur.   

    > [!NOTE]  
    > Les <STRONG> &lt; paramètres &gt; </STRONG> automatiques appliquent les paramètres d’installation du serveur par défaut et sont appliqués automatiquement par le serveur.


Pour autoriser les utilisateurs à inviter des utilisateurs anonymes à des conférences, vous devez aussi activer la prise en charge des utilisateurs anonymes dans votre organisation. Pour plus d’informations, voir [Configurer des stratégies pour contrôler l’accès des](../external-access-policies/configure-policies-to-control-public-user-access.md)utilisateurs publics dans Skype Entreprise Server .

