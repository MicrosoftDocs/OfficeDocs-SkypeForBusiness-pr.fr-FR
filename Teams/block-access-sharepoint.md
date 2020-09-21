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
description: En savoir plus sur la façon de bloquer l’accès à SharePoint pour des utilisateurs spécifiques
ms.openlocfilehash: a2cfdb938dc11d38303df59061db1c46e5b08fcc
ms.sourcegitcommit: 448606977ee67befbdc91060363cf90dd346a528
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/19/2020
ms.locfileid: "48135928"
---
# <a name="block-access-to-sharepoint-for-specific-users"></a>Bloquer l’accès à SharePoint pour des utilisateurs spécifiques

L’application d’une stratégie d’accès conditionnel (CA) sur SharePoint dans Microsoft 365 est également appliquée aux équipes. Toutefois, certaines organisations veulent bloquer l’accès aux fichiers SharePoint (Télécharger, télécharger, afficher, modifier, créer) et permettre à leurs employés d’utiliser les clients de bureau, mobiles et Web teams sur des appareils non gérés. Dans les règles de stratégie d’autorité de certification, le blocage de SharePoint entraînerait le blocage des équipes. Cet article explique comment vous pouvez contourner cette limitation et permettre à vos employés de continuer à utiliser teams tout en bloquant complètement l’accès aux fichiers stockés dans SharePoint.

> [!Note]
> Bloquer ou limiter l’accès sur des appareils non gérés repose sur les stratégies d’accès conditionnel d’Azure AD. En savoir plus sur la gestion des [licences Azure ad](https://azure.microsoft.com/pricing/details/active-directory/). Pour obtenir une vue d’ensemble de l’accès conditionnel dans Azure AD, voir [accès conditionnel dans Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/overview). Pour plus d’informations sur les stratégies d’accès SharePoint Online recommandées, voir recommandations en matière [de stratégie pour la sécurisation des sites et fichiers SharePoint](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies). Si vous limitez l’accès à des appareils non gérés, les utilisateurs sur les appareils gérés doivent utiliser l’une des [combinaisons de systèmes d’exploitation et navigateurs pris en charge](https://docs.microsoft.com/azure/active-directory/conditional-access/technical-reference#client-apps-condition), ou leur accès est également limité.

Vous pouvez bloquer ou limiter l’accès pour :

- Utilisateurs de l’organisation ou seulement certains utilisateurs ou groupes de sécurité.

- Tous les sites au sein de l’organisation ou seulement des sites.

Lorsque l’accès est bloqué, un message d’erreur s’affiche. Bloquez l’accès pour renforcer la sécurité et protéger les données sécurisées. Lorsque l’accès est bloqué, un message d’erreur s’affiche.

1. Ouvrez le [Centre d’administration](https://admin.microsoft.com/sharepoint?page=accessControl&modern=true)SharePoint.

2. Développez stratégies d' **Policies**  >  **accès aux**stratégies.

3. Dans la section **appareils non gérés** , sélectionnez **bloquer l’accès** et sélectionnez **Enregistrer**.

   ![section périphériques non gérés pour les stratégies](media/no-sharepoint-access1.png)

4. Ouvrez le portail [Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) et naviguez jusqu’à **stratégies d’accès conditionnel**.

    Vous verrez une nouvelle stratégie créée par SharePoint, semblable à cet exemple :

    ![nouvelle stratégie nommée utilisation de restrictions appliquées par l’application pour l’accès au navigateur](media/no-sharepoint-access2.png)

5. Mettez à jour la stratégie pour cibler uniquement des utilisateurs ou un groupe spécifiques.

    ![Centre d’administration SharePoint avec l’option Sélectionner l’utilisateur en surbrillance.](media/no-sharepoint-access2b.png)

  > [!Note]
> La définition de cette stratégie entraîne la réduction de votre accès au portail d’administration SharePoint. Nous vous recommandons de configurer la stratégie d’exclusion et de sélectionner les administrateurs généraux et SharePoint.

6. Vérifier que seul SharePoint est sélectionné comme application Cloud ciblée

    ![SharePoint est sélectionné en tant qu’application ciblée.](media/no-sharepoint-access3.png)

7. Vous pouvez également mettre à jour des **conditions** pour inclure des clients de bureau.

    ![mise en surbrillance des applications de bureau et mobiles.](media/no-sharepoint-access4.png)

8. Vérifier que **l’option autoriser l’accès** est activée

    ![l’accès accordé est activé.](media/no-sharepoint-access5.png)

9. Assurez-vous que l’option **utiliser les restrictions** appliquées aux applications est activée.

10. Activez votre stratégie, puis sélectionnez **Enregistrer**.

    ![L’application restrictions appliquée est activée.](media/no-sharepoint-access6.png)

Pour tester votre stratégie, vous devez vous déconnecter de n’importe quel client, tel que l’application de bureau teams ou le client de synchronisation OneDrive entreprise, puis vous reconnecter pour voir la stratégie qui fonctionne. Si votre accès a été bloqué, un message s’affiche dans Microsoft Teams, qui indique que l’élément n’existe pas.

 ![Message élément introuvable.](media/access-denied-sharepoint.png)

Dans SharePoint, vous recevez un message accès refusé.

![Le message accès refusé.](media/blocked-access-warning.png)

## <a name="related-topics"></a>Sujets associés

[Contrôler l’accès pour les appareils non gérés dans SharePoint](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)
