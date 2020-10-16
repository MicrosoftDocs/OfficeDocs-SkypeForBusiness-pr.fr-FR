---
title: Bloquer l’accès à SharePoint pour des utilisateurs spécifiques
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: Nigolc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Découvrez comment bloquer l’accès à SharePoint pour des utilisateurs spécifiques
ms.openlocfilehash: edcdb8286ff69557215a0e481b12e67b81f440fe
ms.sourcegitcommit: 3db7c450d3afbc1049e1016d51016442e5764634
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203837"
---
# <a name="block-access-to-sharepoint-for-specific-users"></a>Bloquer l’accès à SharePoint pour des utilisateurs spécifiques

Toute stratégie d’accès conditionnel appliquée sur SharePoint dans Microsoft 365 est également appliquée à Teams. Toutefois, certaines organisations souhaitent bloquer l’accès aux fichiers SharePoint (chargement, téléchargement, affichage, modification et création), et permettre à leurs employés d’utiliser les clients Teams de bureau, mobiles et web sur les appareils non gérés. Dans les règles de stratégie d’accès conditionnel, le blocage de SharePoint conduirait également au blocage de Teams. Cet article décrit la manière dont vous pouvez contourner cette limitation et permettre à vos employés de continuer à utiliser Teams tout en bloquant l’accès aux fichiers stockés dans SharePoint.

> [!Note]
> Le blocage ou la limitation de l’accès sur des appareils non gérés s’appuie sur les stratégies d’accès conditionnel Azure AD. En savoir plus sur la [gestion des licences Azure AD](https://azure.microsoft.com/pricing/details/active-directory/). Pour obtenir une vue d’ensemble de l’accès conditionnel dans Azure AD, voir [Accès conditionnel dans Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/overview). Pour plus d’informations sur les stratégies d’accès SharePoint Online recommandées, voir [Recommandations en matière de stratégie pour la sécurisation des sites et fichiers SharePoint](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies). Si vous limitez l’accès sur des appareils non gérés, les utilisateurs sur les appareils gérés doivent utiliser l’une des [combinaisons de systèmes d’exploitation et de navigateurs prises en charge](https://docs.microsoft.com/azure/active-directory/conditional-access/technical-reference#client-apps-condition). Dans le cas contraire, ils disposeront également d’un accès limité.

Vous pouvez bloquer ou limiter l’accès pour :

- Les utilisateurs de l’organisation, ou certains utilisateurs ou groupes de sécurité uniquement.

- Tous les sites de votre organisation, ou certains sites uniquement.

Lorsque l’accès est bloqué, les utilisateurs voient un message d’erreur. Le blocage de l’accès renforce la sécurité et protège les données sécurisées. Lorsque l’accès est bloqué, les utilisateurs voient un message d’erreur.

1. Ouvrez le Centre d’administration SharePoint.

2. Développez **Politiques** > **Stratégies d’accès**.

3. Dans la section **Appareils non gérés**, sélectionnez **Bloquer l’accès**, puis **Enregistrer**.

   ![la section Appareils non gérés pour les stratégies](media/no-sharepoint-access1.png)

4. Ouvrez le portail [Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) et accédez à **Stratégies d’accès conditionnel**.

    Une nouvelle stratégie semblable à celle-ci est créée par SharePoint :

    ![une nouvelle stratégie nommée Utiliser les restrictions appliquées par l’application pour l’accès au navigateur](media/no-sharepoint-access2.png)

5. Mettez à jour la stratégie pour cibler uniquement des utilisateurs spécifiques ou un groupe.

    ![centre d’administration SharePoint avec la section Sélectionner un utilisateur mise en évidence.](media/no-sharepoint-access2b.png)

  > [!Note]
> La définition de cette stratégie permettra de réduire l’accès au portail d’administration SharePoint. Nous vous recommandons de configurer la stratégie d’exclusion et de sélectionner les administrateurs globaux et SharePoint.

6. Vérifiez que seul SharePoint est sélectionné en tant qu’application cloud ciblée

    ![SharePoint est sélectionné en tant qu’application ciblée.](media/no-sharepoint-access3.png)

7. Mettez à jour les **conditions** afin d’inclure également les clients de bureau.

    ![applications de bureau et mobiles mises en évidence.](media/no-sharepoint-access4.png)

8. Assurez-vous que l’option **Accorder l’accès** est activée.

    ![l’option Accorder l’accès est activée.](media/no-sharepoint-access5.png)

9. Assurez-vous que **Utiliser les restrictions appliquées par l’application** est activé.

10. Activez votre stratégie et sélectionnez **Enregistrer**.

    ![Les restrictions appliquées par l’application sont activées.](media/no-sharepoint-access6.png)

Pour tester votre stratégie, vous devez vous déconnecter de n’importe quel client, par exemple, l’application de bureau Teams ou le client de synchronisation OneDrive Entreprise, puis vous reconnecter afin d’afficher la stratégie active. Si votre accès a été bloqué, un message indiquant qu’il n’est peut-être pas disponible s’affiche dans Teams.

 ![Message concernant l’élément introuvable.](media/access-denied-sharepoint.png)

Dans SharePoint, vous recevrez un message d’accès refusé.

![Message d’accès refusé.](media/blocked-access-warning.png)

## <a name="related-topics"></a>Voir aussi

[Contrôler l’accès des appareils non gérés dans SharePoint](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)
