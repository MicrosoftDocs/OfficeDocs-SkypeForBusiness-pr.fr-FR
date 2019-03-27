---
title: Affectation des stratégies de conférence pour la prise en charge les utilisateurs anonymes
ms.reviewer: ''
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48184333
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Déterminer qui peut inviter des utilisateurs anonymes en configurant une stratégie de conférence pour prendre en charge les utilisateurs anonymes et appliquer cette stratégie de conférence à des utilisateurs spécifiques.
ms.openlocfilehash: 62ff84b19fadbeaf0f26fa3e5869026254d28d1f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881126"
---
# <a name="assign-conferencing-policies-to-support-anonymous-users-in-skype-for-business-server"></a>Affecter des stratégies de conférence pour prendre en charge les utilisateurs anonymes Skype pour Business Server 


Par défaut, tous les utilisateurs ne peuvent pas d’inviter des utilisateurs anonymes à participer à une réunion. Déterminer qui peut inviter des utilisateurs anonymes en configurant une stratégie de conférence pour prendre en charge les utilisateurs anonymes et appliquer cette stratégie de conférence à des utilisateurs spécifiques. Pour plus d’informations sur la façon de configurer un stratégies de conférence pour prendre en charge les utilisateurs anonymes, voir [créer des stratégies de conférence de Skype pour Business Server](../../conferencing/create-policies.md) et [Managing fédération et accès externe aux Skype pour Business Server](../managing-federation-and-external-access.md).

Utilisez la procédure de cette section pour appliquer une stratégie de conférence que vous avez déjà créée à un ou plusieurs utilisateurs ou groupes d’utilisateurs.

> [!NOTE]  
> Outre la configuration et l’application d’une stratégie pour permettre aux utilisateurs d’inviter des utilisateurs anonymes, vous devez également activer la prise en charge pour les utilisateurs anonymes pour votre organisation. Pour plus d’informations, voir [Configuration des stratégies pour contrôler l’accès des utilisateurs publics dans Skype pour Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).


## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a>Pour configurer une stratégie d’utilisateur pour la participation anonyme aux réunions

1.  À partir d’un compte d’utilisateur qui est membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou est affecté au rôle CsAdministrator, ouvrez une session sur n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business. 

3.  Dans la barre de navigation de gauche, cliquez sur **conférence**, puis effectuez l’une des options suivantes :
    
    1.  Pour créer une nouvelle stratégie utilisateur, cliquez sur **Nouveau**, puis cliquez sur **stratégie de l’utilisateur**. Créez un nom unique dans le champ **nom** qui indique quel traite de la stratégie utilisateur (par exemple, **EnableAnonymous** pour une stratégie d’utilisateur qui permet les communications avec les utilisateurs anonymes).
    
    2.  Pour configurer une stratégie utilisateur existante, cliquez sur la stratégie appropriée dans le tableau, cliquez sur **Modifier**, puis cliquez sur **Afficher les détails**.

4.  Dans la boîte de dialogue **Stratégies de conférence** , activez la case à cocher **Autoriser les participants à inviter des utilisateurs anonymes** .

5.  Cliquez sur **Valider**.

6.  Dans la barre de navigation de gauche, cliquez sur **utilisateurs**, puis recherchez le compte d’utilisateur que vous souhaitez configurer.

7.  Dans le tableau répertoriant les résultats de la recherche, cliquez sur le compte d’utilisateur, sur **Modifier**, puis sur **Afficher les détails**.

8.  Dans **Modifier les Skype pour l’utilisateur Business Server** sous **stratégie de conférence**, sélectionnez la stratégie d’utilisateur avec la configuration de l’accès utilisateur anonyme que vous souhaitez appliquer à cet utilisateur.  

    > [!NOTE]  
    > Le <STRONG> &lt;automatique&gt; </STRONG> paramètres s’appliquent les paramètres d’installation de serveur par défaut et sont appliqués automatiquement par le serveur.


Pour permettre aux utilisateurs d’inviter des utilisateurs anonymes à des conférences, vous devez également activer la prise en charge pour les utilisateurs anonymes dans votre organisation. Pour plus d’informations, voir [Configuration des stratégies pour contrôler l’accès des utilisateurs publics dans Skype pour Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).

