---
title: Affectation des stratégies de conférence pour la prise en charge les utilisateurs anonymes
ms.reviewer: ''
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48184333
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Vous contrôlez qui peut inviter des utilisateurs anonymes en configurant une stratégie de conférence pour prendre en charge les utilisateurs anonymes et en appliquant cette stratégie de conférence à des utilisateurs spécifiques.
ms.openlocfilehash: d7956e68db3330f0804e6161e0eeaf52958bc588
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280284"
---
# <a name="assign-conferencing-policies-to-support-anonymous-users-in-skype-for-business-server"></a>Attribution de stratégies de conférence pour prendre en charge les utilisateurs anonymes dans Skype entreprise Server 


Par défaut, tous les utilisateurs ne peuvent pas inviter des utilisateurs anonymes à participer à une réunion. Vous contrôlez qui peut inviter des utilisateurs anonymes en configurant une stratégie de conférence pour prendre en charge les utilisateurs anonymes et en appliquant cette stratégie de conférence à des utilisateurs spécifiques. Pour plus d’informations sur la configuration des stratégies de conférence pour prendre en charge les utilisateurs anonymes, reportez-vous à la rubrique [création de stratégies de conférence dans Skype entreprise Server](../../conferencing/create-policies.md) et gestion de la [Fédération et de l’accès externe à Skype entreprise Server](../managing-federation-and-external-access.md).

Suivez la procédure décrite dans cette section pour appliquer une stratégie de conférence que vous avez déjà créée à un ou plusieurs utilisateurs ou groupes d’utilisateurs.

> [!NOTE]  
> En plus de configurer et d’appliquer une stratégie pour permettre aux utilisateurs d’inviter des utilisateurs anonymes, vous devez également activer la prise en charge des utilisateurs anonymes pour votre organisation. Pour plus d’informations, reportez-vous à la rubrique [Configuration des stratégies pour contrôler l’accès des utilisateurs publics dans Skype entreprise Server](../external-access-policies/configure-policies-to-control-public-user-access.md).


## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a>Pour configurer une stratégie utilisateur pour la participation anonyme aux réunions

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsAdministrator, connectez-vous à n’importe quel ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server. 

3.  Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis effectuez l’une des opérations suivantes:
    
    1.  Pour créer une nouvelle stratégie d’utilisateur, cliquez sur **nouveau**, puis cliquez sur stratégie de l' **utilisateur**. Dans le champ **nom** , créez un nom unique qui indique l’objet de la stratégie de l’utilisateur (par exemple, **EnableAnonymous** pour une stratégie utilisateur qui autorise les communications avec des utilisateurs anonymes).
    
    2.  Pour configurer une stratégie d’utilisateur existante, cliquez sur la stratégie appropriée répertoriée dans le tableau, cliquez sur **modifier**, puis sur **afficher les détails**.

4.  Dans la boîte de dialogue **stratégies de conférence** , activez la case à cocher **autoriser les participants à inviter des utilisateurs anonymes** .

5.  Cliquez sur **Valider**.

6.  Dans la barre de navigation de gauche, cliquez sur **utilisateurs**, puis recherchez le compte d’utilisateur que vous voulez configurer.

7.  Dans le tableau répertoriant les résultats de la recherche, cliquez sur le compte d’utilisateur, sur **Modifier**, puis sur **Afficher les détails**.

8.  Dans **modifier l’utilisateur de Skype entreprise Server** sous **stratégie de conférence**, sélectionnez la stratégie de l’utilisateur avec la configuration d’accès anonyme pour les utilisateurs que vous souhaitez appliquer à cet utilisateur.  

    > [!NOTE]  
    > Les <STRONG> &lt;paramètres&gt; automatiques</STRONG> appliquent les paramètres d’installation par défaut du serveur et sont appliqués automatiquement par le serveur.


Pour permettre aux utilisateurs d’inviter des utilisateurs anonymes à des conférences, vous devez également activer la prise en charge des utilisateurs anonymes au sein de votre organisation. Pour plus d’informations, reportez-vous à la rubrique [Configuration des stratégies pour contrôler l’accès des utilisateurs publics dans Skype entreprise Server](../external-access-policies/configure-policies-to-control-public-user-access.md).

