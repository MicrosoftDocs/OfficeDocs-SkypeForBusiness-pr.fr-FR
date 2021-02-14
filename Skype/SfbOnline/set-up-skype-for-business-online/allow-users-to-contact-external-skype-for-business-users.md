---
title: Autoriser les utilisateurs à contacter des utilisateurs externes de Skype Entreprise
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: b414873a-0059-4cd5-aea1-e5d0857dbc94
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Setup
- For O365M_ShareLync
- ms.lync.lac.OrgExternalAccess
- ms.lync.lac.skypefederation
- O365E_HRCLYNC _ SipFederationSrvRecordVerified_FL312122
- O365E_ShareLync
- O365M_ShareLync
- O365P_ExternalCommDesc
- O365P_ShareLync
- LIL_Placement
description: 'Découvrez comment configurer Skype Entreprise pour laisser les utilisateurs parler aux utilisateurs d’une autre organisation ou laisser des contacts extérieurs parler à eux. '
ms.openlocfilehash: d9b3be381432fa95962df7a5a58ea9d81e223fc4
ms.sourcegitcommit: 619b68d28b4fbf8b5296d95bbc7ed566f839f1db
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/20/2020
ms.locfileid: "48625050"
---
# <a name="allow-users-to-contact-external-skype-for-business-users"></a>Autoriser les utilisateurs à contacter des utilisateurs externes de Skype Entreprise
  
Suivez la procédure décrite dans cet article lorsque :
  
- Vous avez des utilisateurs avec des domaines différents dans votre entreprise. Par exemple, Rob@ContosoEast.com et Ann@ContosoWest.com.

- Vous souhaitez que les personnes de votre organisation utilisent Skype Entreprise pour contacter des membres d'entreprises spécifiques en dehors de votre organisation.

- Vous souhaitez que les autres utilisateurs de Skype Entreprise à travers le monde puissent vous contacter à l’aide de votre adresse e-mail. S’ils utilisent les paramètres Skype Entreprise par défaut et vous-même, cela fonctionne automatiquement. Si ce n’est pas le cas, ils devront s’assurer que leur configuration ne bloque pas votre domaine.

## <a name="enable-business-to-business-communications-for-your-users"></a>Autoriser les communications entre entreprises pour vos utilisateurs

<a name="bk_preview"> </a>

Pour ce faire, vous devez avoir des [autorisations](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) d’administrateur dans Microsoft 365 ou Office 365 dans les deux organisations.

![Icône montrant le logo Microsoft Teams à ](../images/teams-logo-30x30.png) **l’aide du Centre d’administration Teams**
  
1. Connectez-vous à l’aide de votre compte d’administrateur Microsoft 365 ou Office 365.

2. Dans le Centre d’administration, allez dans **Centres d’administration**  >  **Teams.**

    ![Sélectionnez l’administrateur de Teams.](../images/MS-Teams-Admin.png)
  
3. Dans le **Centre Teams,** **sélectionnez portail hérité** >  
  ![ Skype, choisissez le portail hérité SfB.](../images/SFBlegacy-size65.png)

4. Dans la **Centre d’administration Skype Entreprise**, sélectionnez **Organisation** > **Communications externes**.
5. Pour configurer une communication avec une entreprise particulière ou avec des utilisateurs ayant un autre domaine, dans le menu déroulant, choisissez **Activé uniquement pour les domaines autorisés**.

    Ou, si vous souhaitez activer les communications avec toute personne disposant de stratégies Skype Entreprise ouvertes, sélectionnez **Activer sauf pour les domaines bloqués**. Il s'agit du paramètre par défaut.

6. Sous **Domaines bloqués ou autorisés,** choisissez et ajoutez le nom du **+** domaine que vous voulez autoriser.

7. Assurez-vous que l’administrateur de l’autre organisation doit effectuer les mêmes étapes dans le Centre **d’administration Skype Entreprise.** Par exemple, dans sa liste de **domaines autorisés**, l'administrateur de l'autre organisation doit entrer le domaine de votre entreprise.

8. Si vous utilisez le pare-feu Windows, Skype Entreprise ouvre automatiquement les ports nécessaires.

    Si votre organisation utilise un pare-feu différent pour restreindre l'accès à Internet des ordinateurs de votre réseau, assurez-vous que vos ordinateurs clients peuvent accéder aux [URL et plages d'adresses IP Office 365](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges) suivants. Cela peut nécessiter l’ajout des FQDN à la liste de votre pare-feu ou de votre configuration d’infrastructure proxy : **\* .api.skype.com,** \* **.users.storage.live.com** et **graph.skype.com.** Pour obtenir des instructions sur la façon d’ouvrir ces ports dans votre pare-feu, consultez la documentation qui l’intait.

    Pour obtenir la liste de tous les ports que vous devez ouvrir, voir URL et [plages d’adresses IP Office 365.](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges)

9. Assurez-vous que l’administrateur de l’organisation a également suivi ces étapes.

10. **ATTENDEZ JUSQU’À 24 HEURES POUR EFFECTUER UN TEST**. Lorsque vous modifiez les paramètres de communications externes, jusqu’à 24 heures peuvent être nécessaires avant que les modifications ne s’insérez dans tous les centres de données.

![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) Vous pouvez permettre à vos utilisateurs de rechercher et contacter par messagerie instantanée toute personne utilisant l'application gratuite Skype. Pour en savoir plus, voir [Laisser les utilisateurs de Skype Entreprise ajouter des contacts Skype.](let-skype-for-business-users-add-skype-contacts.md)
  
## <a name="test-and-troubleshoot"></a>Test et dépannage

<a name="bk_preview"> </a>

 **Le problème que les utilisateurs rencontrent le plus souvent lors de la configuration de la communication entre entreprises est lié aux [URL et plages d'adresses IP Office 365](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges).**
  
Pour tester votre configuration, vous devez disposer d'un contact Skype Entreprise qui ne soit pas situé derrière le pare-feu de votre entreprise.
  
1. Une fois vos paramètres de communication externe modifiés, **ATTENDEZ JUSQU'À 24 HEURES POUR EFFECTUER UN TEST**.

2. Dans Skype Entreprise, recherchez votre contact dans Skype Entreprise et envoyer une demande de discussion.

    Si vous recevez un message vous savez qu’il n’a pas pu être envoyé en raison d’une stratégie d’entreprise, vous devez vérifier à nouveau vos URL et [plages d’adresses IP Office 365.](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges)

3. Demandez à votre contact Skype Entreprise de vous envoyer une demande de discussion. Si vous ne la recevez pas, le problème se situe au niveau de vos paramètres de pare-feu (en supposant que votre contact a confirmé que ses paramètres sont corrects).

4. Une autre façon de vérifier si le problème se trouve au-de pare-feu consiste à utiliser un emplacement Wifi qui n’est pas derrière votre pare-feu, par exemple un café. Utilisez Skype Entreprise pour envoyer une demande de discussion à votre contact. Si le message est correctement envoyé, cela signifie que le problème est lié à votre pare-feu.

## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a>Comment trouver des personnes et être trouvé lors d'une connexion avec une autre entreprise.

<a name="bk_preview"> </a>

Une fois la communication externe activée avec d’autres utilisateurs de Skype Entreprise, vos utilisateurs peuvent trouver des utilisateurs Skype Entreprise fédérés en recherchant leur nom de signature. C’est le cas, par exemple, Rob@contoso.com. Ils devront ensuite ajouter la personne à leurs listes de contacts.
  
![Pour rechercher un utilisateur dans une entreprise fédérée, vous devez rechercher son adresse de messagerie (il s’agit généralement également de son nom de sign in).](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a>Conseils de configuration des communications avec des entreprises fédérées

<a name="bk_preview"> </a>

- Pour configurer la fédération entre Skype Entreprise 2015 et Skype Entreprise Online, consultez cet article : Configurer la fédération avec [Skype Entreprise Online.](https://technet.microsoft.com/library/jj205126.aspx)

- Pour configurer la fédération entre Lync et Skype Entreprise Online, consultez cet article : Configuration de la prise en charge de la fédération pour un client [Lync Online.](https://technet.microsoft.com/library/hh202193.aspx)

- Lorsque deux utilisateurs de Skype Entreprise dans Microsoft 365 ou Office 365 communiquent entre eux sur des domaines distincts, ils peuvent uniquement utiliser les fonctionnalités de Skype Entreprise (par exemple, les conversations vidéo ou le partage de bureau) qui sont sous l’une ou l’autre des deux organisations.

- Si un utilisateur Skype Entreprise de votre organisation est placé en In-Place ou en attente pour litige, toutes les conversations par messagerie instantanée entre cet utilisateur et d’autres utilisateurs Skype Entreprise ou Skype sont enregistrées dans les éléments **récupérables** de leur boîte aux lettres. Ces conversations ne sont pas enregistrées dans le dossier **Historique des conversations** de leur boîte aux lettres.

## <a name="turn-off-external-communication-for-specific-individuals"></a>Désactiver la communication externe pour des individus spécifiques

<a name="bk_preview"> </a>

Après l'activation de la communication externe pour l'ensemble de votre entreprise, vous pouvez la désactiver pour des individus spécifiques.
  
1. Connectez-vous à l’aide de votre compte d’administrateur Microsoft 365 ou Office 365.

2. Dans le Centre d’administration, voir **Utilisateurs**  >  **actifs.**

3. Dans la liste des utilisateurs, choisissez l'utilisateur, puis sous **Paramètres supplémentaires**, cliquez sur **Modifier les propriétés de Skype Entreprise**.

    ![Choose Skype for Business](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. Dans le Centre **d’administration Skype Entreprise,** sélectionnez **Communications externes.**

    Dans la page **Options,** toutes les options sont sélectionnées. Désactivez les communications que vous voulez désactiver. L'image suivante indique que Jakob pourra communiquer avec le personnel d'autres entreprises approuvées, mais pas avec d'autres utilisateurs Skype.

    ![Choose External contacts](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. Cliquez sur **Enregistrer**.

> [!NOTE]
> Il est possible que les modifications ne prennent effet qu'après 24 heures.
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]

## <a name="related-topics"></a>Sujets associés

<a name="bk_preview"> </a>

[Configurer Skype Entreprise Online](set-up-skype-for-business-online.md)
  
[Autoriser les utilisateurs Skype Entreprise à ajouter des contacts Skype](let-skype-for-business-users-add-skype-contacts.md)
  