---
title: Gérer les comptes de ressource dans Teams
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.reviewer: jastark, wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
- seo-marvel-apr2020
description: Dans cet article, vous allez apprendre à créer, modifier et gérer des comptes de ressources dans Microsoft Teams.
ms.openlocfilehash: 2bc0642f20341b9818b1c407fa0294127ee44d6a
ms.sourcegitcommit: ae687f530d5505b96df7cb7ef4da3a36bd9afd29
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/10/2023
ms.locfileid: "69763575"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a>Gérer les comptes de ressources dans Microsoft Teams

[!INCLUDE [set-up-resource-account-steps](./includes/set-up-resource-account-steps.md)]

## <a name="next-steps"></a>Étapes suivantes

Une fois que vous avez terminé la configuration du compte de ressource et que vous avez affecté un numéro de téléphone si nécessaire, vous êtes prêt à utiliser le compte de ressource avec un standard automatique ou une file d’attente d’appels.

Pour en savoir plus, consultez les références suivantes :

- [Standard automatique cloud](create-a-phone-system-auto-attendant.md)
- [File d’attente d’appels cloud](create-a-phone-system-call-queue.md)

Vous pouvez modifier le nom **d’affichage** et le type **de compte de ressource** du compte de ressource à l’aide de l’option **Modifier** . Sélectionnez **Enregistrer** lorsque vous avez terminé.

## <a name="change-an-existing-resource-account-to-use-a-microsoft-teams-phone-resource-account-license"></a>Modifier un compte de ressource existant pour utiliser une licence de compte de ressource Téléphonie Microsoft Teams

Pour basculer les licences de votre compte de ressources existant d’une licence **Téléphonie Teams standard** à une licence **de compte de ressource Téléphonie Microsoft Teams**, vous devez acquérir la licence **de compte** de ressource Téléphonie Microsoft Teams, puis suivre les étapes décrites dans le Centre d'administration Microsoft 365 [déplacer les utilisateurs vers un autre abonnement](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).

> [!WARNING]
> Supprimez toujours une licence **Téléphonie Teams standard** et attribuez la licence **de compte de ressource Téléphonie Microsoft Teams** dans la même activité de licence. Si vous supprimez l’ancienne licence, enregistrez les modifications du compte, ajoutez la nouvelle licence, puis enregistrez à nouveau les paramètres du compte, le compte de ressource risque de ne plus fonctionner comme prévu. Dans ce cas, nous vous recommandons de créer un compte de ressource pour la licence **de compte de ressource Téléphonie Microsoft Teams** et de supprimer le compte de ressource rompu.

## <a name="skype-for-business-server-2019"></a>Skype Entreprise Server 2019

Pour les comptes de ressources hébergés sur Skype Entreprise Server 2019 qui peuvent être utilisés avec des files d’attente d’appels cloud et des standards automatiques cloud, voir [Planifier les files d’attente d’appels cloud](/SkypeforBusiness/hybrid/plan-call-queue) ou [Planifier les standards automatiques cloud](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant). Les implémentations hybrides (numéros hébergés sur le routage direct) sont configurées à l’aide de l’applet de commande [New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint) sur un serveur Skype Entreprise Server 2019 local.

Les ID d’application que vous devez utiliser lors de la création des instances d’application sont les suivants :

- **Standard automatique :** ce933385-9390-45d1-9512-c8d228074e07
- **File d’attente des appels :** 11cd3e2e-fccb-42ad-ad00-878b93575e07

> [!NOTE]
> Si vous souhaitez que la file d’attente d’appels ou le standard automatique puisse faire l’objet d’une recherche par les utilisateurs de Skype Entreprise Server 2019, vous devez créer vos comptes de ressources sur Skype Entreprise Server 2019, car les comptes de ressources en ligne ne sont pas synchronisés avec Active Directory. Lorsque les enregistrements SRV DNS pour sipfederationtls sont résolus en Skype Entreprise Server 2019, les comptes de ressources **doivent** être créés sur Skype Entreprise Server 2019 à l’aide de l’interpréteur de commandes SfB Management et synchronisés avec Azure AD.

Pour les implémentations hybrides avec Skype Entreprise Server :

- [Planifier les standards automatiques cloud](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant).
- [Planifier les files d’attente d’appels cloud](/SkypeforBusiness/hybrid/plan-call-queue).
- [Configurez des comptes de ressources locaux](/SkypeForBusiness/hybrid/configure-onprem-ra).

## <a name="delete-a-resource-account"></a>Supprimer un compte de ressource

Veillez à dissocier le numéro de téléphone du compte de ressource avant de le supprimer pour éviter que votre numéro de téléphone ne soit bloqué en mode en attente.

Après cela, vous pouvez supprimer le compte de ressource dans le Centre d'administration Microsoft 365, sous l’onglet **Utilisateurs**.

Pour dissocier un numéro de téléphone de routage direct du compte de ressource, utilisez l’applet de commande suivante :

```powershell
Remove-CsPhoneNumberAssignment -Identity <Resource Account Object ID> -PhoneNumber <assigned phone number> -PhoneNumberType DirectRouting
```

## <a name="hide-resource-accounts-from-teams-users"></a>Masquer les comptes de ressources des utilisateurs Teams

Vous souhaiterez peut-être masquer certains comptes de ressources aux utilisateurs Teams. Par exemple, vous pouvez empêcher les utilisateurs de Teams d’appeler directement une file d’attente d’appels et de contourner le standard automatique où les heures d’opération sont configurées.

[Les barrières à l’information](information-barriers-in-teams.md) sont utilisées pour masquer les comptes de ressources.  Passez en revue la documentation sur les obstacles à l’information pour comprendre les impacts possibles avant de procéder aux étapes ci-dessous.

### <a name="required-subscriptions-and-permissions"></a>Abonnements et autorisations requis 

Pour accéder aux obstacles à l’information et les utiliser, votre organisation doit disposer de l’un des abonnements ou modules complémentaires suivants : 

-   abonnement Microsoft 365 E5/A5 (version payante ou d’évaluation).
-   Abonnement Office 365 E5/A5/A3/A1 (version payante ou d’évaluation).
-   Conformité avancée Office 365 module complémentaire.
-   Abonnement Microsoft 365 E3/A3/A1 + module complémentaire conformité Microsoft 365 E5/A5.
- abonnement Microsoft 365 E3/A3/A1 + le module complémentaire gestion des risques internes Microsoft 365 E5/A5.

> [!NOTE]
> Si vous avez déjà [Exchange Online](/exchange/address-books/address-book-policies/address-book-policies) stratégies de carnet d’adresses configurées, elles doivent être supprimées avant de procéder aux étapes ci-dessous.   
> 
> Toutes les étapes ci-dessous sont effectuées par l’administrateur général du locataire. 
>   
> Ces instructions supposent qu’il n’y a pas d’autres obstacles à l’information configurés.

#### <a name="teams-admin-center"></a>Centre d’administration Microsoft Teams

1. Connectez-vous au [Centre d’administration Teams](https://go.microsoft.com/fwlink/p/?linkid=2066851).
2. Dans le menu de gauche, développez **Teams**.
3. Sélectionnez **Paramètres Teams**. 
4. Faites défiler vers le bas jusqu’à **Rechercher par nom**.
5. Activez le bouton bascule et enregistrez la modification.

Pour plus d’informations sur cette option, consultez [Limiter les utilisateurs qui peuvent voir lors de la recherche dans l’annuaire dans Teams](teams-scoped-directory-search.md).

#### <a name="compliance---auditing"></a>Conformité - Audit

1. Connectez-vous au [portail de conformité Microsoft Purview](https://compliance.microsoft.com/).
2. Dans le volet de navigation gauche, sélectionnez **Auditer**.
3. Si l’audit est désactivé, la bannière suivante s’affiche : 
 
     :::image type="content" source="/microsoft-365/media/AuditingBanner.png" alt-text="Capture d’écran montrant la bannière d’audit si l’audit n’est pas activé":::
  
4. Sélectionnez **Démarrer l’enregistrement de l’activité utilisateur et administrateur**. 

Pour plus d’informations sur l’audit, consultez [Configurer l’audit (standard) dans Microsoft 365](/microsoft-365/compliance/audit-standard-setup).

#### <a name="segmenting-data"></a>Segmentation des données

Les comptes de ressources qui ne doivent pas être appelés directement doivent être segmentés et facilement identifiables.  Cela peut être fait en les rendant membres d’un groupe particulier ou par des informations uniques dans leur profil utilisateur, telles que : 

-   Société
-   Nom d’utilisateur principal
-   Lieu
-   Service
-   Emplacement d’utilisation
-   Surnom du courrier (alias)
-   Nom du bureau de livraison physique (Office)
-   Code postal
-   Adresse proxy (adresse Email)
-   Adresse postale
-   Adresse cible (ExternalEmailAddress)
-   Mail (WindowsEmailAddress)
-   Description

Dans l’exemple d’étapes ci-dessous, le `Department` champ sera utilisé. 

Pour plus d’informations sur la segmentation des utilisateurs, consultez  [Identifier les segments](/microsoft-365/compliance/information-barriers-policies).

#### <a name="microsoft-admin-center"></a>Centre d’administration Microsoft

1. Connectez-vous au [Centre Administration Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2024339).
2. Dans le volet de navigation gauche, sélectionnez **Utilisateurs actifs**.
3. Sélectionnez le premier compte de ressource auquel bloquer les appels directs.
4. Sélectionnez **Gérer les informations de contact** dans le volet droit.
5. Remplacez le contenu du `Department` champ par un mot ou un acronyme unique qui n’est pas utilisé comme nom de service. Par exemple, `DNC`.
6. Enregistrez les modifications.
7. Répétez cette opération pour chaque compte de ressource qui doit être bloqué pour recevoir des appels directs.

#### <a name="compliance---information-barriers"></a>Conformité - Obstacles à l’information

1. Connectez-vous au [portail de conformité Microsoft Purview](https://compliance.microsoft.com/).
2. Dans le volet de navigation gauche, sélectionnez Barrières  > **d’informations****Segments**.
3. Sélectionnez **Nouveau segment**.
4. Entrez un nom pour le segment, puis sélectionnez **Suivant**. Par exemple, `Uncallable Resource Accounts`.
5. Sélectionnez **+ Ajouter**, puis **Département**.
6. Entrez le mot ou l’acronyme unique utilisé dans l’étape 5 du Centre d’administration Microsoft ci-dessus. Par exemple, `DNC`.
7. Sélectionnez **Suivant**, puis **Envoyer**.
8. Sélectionnez **Nouveau segment**.
9. Entrez un nom pour le segment, puis sélectionnez **Suivant**. Par exemple, `Callable Users`.
10. Sélectionnez **+ Ajouter**, puis **Département**.
11. Sélectionnez la liste déroulante **Égal** à, puis sélectionnez **Non égal à**.
12. Entrez le mot ou l’acronyme unique utilisé dans l’étape 5 du Centre d’administration Microsoft ci-dessus. Par exemple, `DNC`.
13. Sélectionnez **Suivant**, puis **Envoyer**. 
14. Dans le volet de navigation gauche, sélectionnez **Stratégies d’obstacles à l’information** > **.**
15. Sélectionnez **Créer une stratégie**.
16. Entrez un nom pour la stratégie, puis sélectionnez **Suivant**. Par exemple, `Uncallable Resource Accounts`.
17. Sélectionnez **+ Choisir un segment**, ajoutez le segment créé à l’étape 9 ci-dessus, puis sélectionnez **Suivant**. Par exemple, `Callable Users`.
18. Sélectionnez **Bloqué dans** la liste déroulante **Communication et collaboration** .
19. Sélectionnez **+ Choisir un segment**, ajoutez le segment créé à l’étape 4 ci-dessus, puis sélectionnez **Suivant**. Par exemple, `Uncallable Resource Accounts`.
20. Définissez la stratégie **sur Activé**, sélectionnez **Suivant**, puis **Envoyer**.
21. Sélectionnez **Créer une stratégie**.
22. Entrez un nom pour la stratégie, puis sélectionnez **Suivant**. Par exemple, `Callable Users`.
23. Sélectionnez **+ Choisir un segment**, ajoutez le segment créé à l’étape 4, puis sélectionnez **Suivant**.
24. Sélectionnez **Bloqué dans** la liste déroulante **Communication et collaboration** . 
25. Sélectionnez **+ Choisir un segment**, ajoutez le segment créé à l’étape 9 ci-dessus, puis sélectionnez **Suivant**.
26. Définissez la stratégie **sur Activé**, sélectionnez **Suivant**, puis **Envoyer**.
27. Dans le volet de navigation gauche, sélectionnez **Informations barrières** > **Application de stratégie**.
28. Sélectionnez **Appliquer toutes les stratégies**.

> [!NOTE]
> L’application de la stratégie peut prendre 30 minutes ou plus.  
> 
> Une fois l’état terminé, accédez au Client Teams et essayez de rechercher les comptes de ressources qui ont été bloqués. Il peut être nécessaire d’effacer le cache Teams.  
> 
> Si un utilisateur Teams a enregistré le compte de ressource en tant que contact, il ne pourra plus l’appeler.
