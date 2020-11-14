---
title: Gérer l’accès externe (Fédération)
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: vinbel
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.externalaccess.overview
- seo-marvel-mar2020
description: Votre administrateur Teams ou informatique peut configurer l’accès externe pour les autres domaines (Fédération) pour permettre aux utilisateurs de ces domaines de participer à Teams.
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 9739c35fcd22229f3f1115edf029535f9b23e8f9
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031780"
---
<a name="manage-external-access-in-microsoft-teams"></a>Gérer l’accès externe dans Microsoft Teams
======================================================

L’accès externe permet aux utilisateurs de Microsoft teams de rechercher, appeler, discuter et organiser des réunions en équipe. Vous pouvez également utiliser l’accès externe pour communiquer avec des utilisateurs externes qui utilisent encore Skype entreprise (en ligne et sur site) et Skype (en version préliminaire).

> [!NOTE]
> Les domaines autorisés ou bloqués s’appliquent uniquement aux réunions si l’accès anonyme aux réunions est « désactivé ».

Si vous voulez que les utilisateurs externes aient accès aux équipes et aux canaux, l’accès invité sera sans doute préférable. Pour plus d’informations sur les différences entre l’accès externe et l’accès invité, voir [Comparer les accès externe et invité](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access). 

Utilisez l’accès externe dans les situations suivantes :
  
- Vous avez des utilisateurs dans différents domaines qui doivent collaborer. Par exemple, Rob@contoso.com et Ann@northwindtraders.com travaillent ensemble sur un projet en même temps que d’autres personnes dans les domaines contoso.com et northwindtraders.com.

- Vous souhaitez que les membres de votre organisation utilisent Teams pour contacter des personnes appartenant à des entreprises spécifiques extérieures à votre organisation.

- Ou vous souhaitez que tous les utilisateurs de Teams à travers le monde puissent vous contacter, à l'aide de votre adresse électronique. 

> [!IMPORTANT]
> Pour pouvoir utiliser le client teams pour communiquer avec un utilisateur externe (qu’il utilise teams ou Skype entreprise), l’utilisateur de teams doit être hébergé dans Skype entreprise online.

## <a name="plan-for-external-access"></a>Plan pour l’accès externe

Par défaut, l’accès externe est activé dans Teams, ce qui signifie que votre organisation peut communiquer avec tous les domaines externes. Si vous ajoutez des domaines bloqués, tous les autres domaines sont autorisés. Si vous ajoutez des domaines autorisés, tous les autres domaines sont bloqués. Il existe une exception à cette règle, si les participants anonymes sont autorisés à participer à des réunions. Trois scénarios permettent de configurer l’accès externe dans le centre d’administration de Teams ( **Paramètres à l’échelle de l’organisation** > **Accès externe** ) :

- **Fédération ouverte** : il s’agit du paramètre par défaut dans Teams, qui permet aux membres de votre organisation de rechercher, d’appeler, d’envoyer des messages instantanés/conversations et de configurer des réunions avec des personnes extérieures à votre organisation.

    Lorsque vous optez pour cette configuration, vos utilisateurs peuvent communiquer avec tous les domaines externes exécutant Teams ou Skype Entreprise et utilisant la Fédération ouverte OU ayant ajouté votre domaine à leur liste Autoriser.

- **Autoriser des domaines spécifiques** : en ajoutant des domaines à une liste **Autoriser** , vous limitez l’accès externe uniquement aux domaines autorisés. Une fois que vous avez configuré la liste des domaines autorisés, tous les autres domaines sont bloqués. Pour autoriser certains domaines, cliquez sur **Ajouter un domaine** , ajoutez le nom de domaine, cliquez sur **Action à effectuer sur ce domaine** , puis sélectionnez **Autorisé**.

- **Bloquez des domaines spécifiques** -en ajoutant des domaines à une liste **Bloquer** , vous pouvez communiquer avec tous les domaines externes *à l’exception de* ceux que vous avez bloqués. Pour bloquer certains domaines, cliquez sur **Ajouter un domaine** , ajoutez le nom de domaine, cliquez sur **Action à effectuer sur ce domaine** , puis sélectionnez **Bloqué**. Une fois que vous avez configuré la liste des domaines bloqués, tous les autres domaines sont autorisés.

> [!NOTE]
> Si vous désactivez l’accès externe au sein de votre organisation, les utilisateurs externes peuvent tout de même participer à des réunions via une jointure anonyme. Pour en savoir plus, voir [gérer les paramètres de réunion dans teams](https://docs.microsoft.com/microsoftteams/meeting-settings-in-teams).

## <a name="allow-or-block-domains"></a>Autoriser ou bloquer des domaines

### <a name="step-1---enable-your-organization-to-communicate-with-another-teams-or-skype-for-business-organizations"></a>Étape 1 : permettre à votre organisation de communiquer avec d’autres équipes ou des organisations Skype entreprise

![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft Teams**  :

1. Dans le volet de navigation gauche, accédez à **Paramètres à l’échelle de l’organisation** > **Accès externe**.

2. Activez le paramètre **Les utilisateurs peuvent communiquer avec d’autres utilisateurs de Skype Entreprise et de Teams**.

     ![Capture d’écran de Les utilisateurs peuvent communiquer avec d’autres utilisateurs de Skype Entreprise et de Teams activé.](media/manage-external-access-2.png).

3. Si vous voulez autoriser toutes les organisations Teams à communiquer avec des utilisateurs au sein de votre organisation, passez à l’étape 5.

4. Si vous voulez limiter les organisations pouvant communiquer avec les utilisateurs de votre organisation, vous pouvez autoriser tous les domaines sauf certains, ou autoriser uniquement certains domaines. 

    - Pour autoriser tous les domaines sauf certains, ajoutez les domaines que vous voulez bloquer en cliquant sur **Ajouter un domaine**. Dans le volet **Ajouter un domaine** , tapez le nom de domaine, cliquez sur **Bloqué** , puis sur **Terminé**. 
    - Pour limiter les communications à des organisations spécifiques, ajoutez ces domaines à la liste en définissant l’état **Autorisé**. Une fois que vous avez ajouté un domaine à la liste Autoriser, les communications avec d’autres organisations sont limitées aux seules organisations dont les domaines figurent dans la liste Autoriser. 

5. Cliquez sur **Enregistrer**.

6. Assurez-vous que l’administrateur de l’autre organisation Teams effectue les mêmes étapes. Par exemple, dans leur **liste de domaines autorisée** , leur administrateur doit entrer dans le domaine de votre entreprise s’ils limitent les organisations pouvant communiquer avec leurs utilisateurs.

### <a name="step-2---test-it"></a>Étape 2 : tester

Pour tester votre configuration, vous devez disposer d’un contact Teams qui ne soit pas derrière votre pare-feu.
  
1. Une fois que vous et l’administrateur de l’organisation avez modifié les paramètres d’ **Accès externe** , vous devriez être prêt.

2. Dans l’application Teams, recherchez la personne par adresse de messagerie et envoyez une demande de conversation.

3. Demandez à votre contact Teams de vous envoyer une demande de discussion. Si vous ne recevez pas leur demande, le problème est lié aux paramètres de votre pare-feu (en supposant qu’ils aient déjà vérifié que les paramètres de leur pare-feu sont corrects).

4. Une autre méthode pour tester si le problème est lié à votre pare-feu consiste à utiliser un emplacement WiFi non protégé par votre pare-feu. par exemple, un cybercafé, et vous pouvez utiliser Teams pour envoyer une demande de conversation à votre contact. Si le message a pu être envoyé depuis l’emplacement WiFi et non depuis votre bureau, vous savez alors que le problème est lié à votre pare-feu.

> [!NOTE]
> Si vous et un autre utilisateur activez l’accès externe et autorisez les domaines d’un autre utilisateur, cela fonctionnera. Si cela ne fonctionne pas, l’autre utilisateur doit s’assurer que sa configuration ne bloque pas votre domaine.


## <a name="communicate-with-skype-users-in-preview"></a>Communiquer avec les utilisateurs de Skype (en version d’évaluation)

Pour permettre aux membres Teams de votre organisation de discuter avec et d’appeler des utilisateurs de Skype, procédez comme suit. Les membres de Teams peuvent ensuite rechercher et démarrer une conversation texte privée ou un appel audio/vidéo avec des utilisateurs de Skype, et vice-versa.

![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft Teams**  :

1. Dans le volet de navigation gauche, accédez à **Paramètres à l’échelle de l’organisation** > **Accès externe**.

2. Activez le paramètre **Les utilisateurs peuvent communiquer avec les utilisateurs de Skype**.

    ![La capture d’écran du paramètre Les utilisateurs peut communiquer avec Skype activé](media/manage-external-access-5.png).

Pour en savoir plus sur la manière dont les utilisateurs de Teams et les utilisateurs de Skype peuvent communiquer, y compris les limitations qui s’appliquent, voir [Interopérabilité Skype et Teams](teams-skype-interop.md).

## <a name="common-external-access-scenarios"></a>Scénarios d’accès externe courants

Les sections suivantes décrivent l’activation de la Fédération pour les scénarios courants d’accès externe et la façon dont TeamsUpgradePolicy détermine la remise des conversations et appels entrants.

### <a name="enable-federation"></a>Activer la Fédération

Pour permettre aux utilisateurs de votre organisation de communiquer avec des utilisateurs d’une autre organisation, les deux organisations doivent activer la Fédération. Les étapes permettant d’activer la Fédération pour une organisation donnée varient en fonction du mode de connexion, hybride ou purement local de l’organisation.

|**Si votre organisation est** |**Activer la Fédération comme suit**  |
|:---------|:-----------------------|
|Connexion sans Skype entreprise locale. Il s’agit d’organisations incluant des utilisateurs de TeamsOnly et/ou des utilisateurs de Skype entreprise online.| Si vous utilisez le centre d’administration teams : <br>-Assurez-vous que les **utilisateurs peuvent communiquer avec d’autres utilisateurs de Skype entreprise et équipes** dans l’accès externe.<br>-Si vous n’utilisez pas la Fédération d’ouverture (qui autorise la Fédération avec n’importe quel autre domaine), ajoutez le domaine externe à la liste autorisée.<br><br>Si vous utilisez PowerShell :<br>-Vérifiez que le client est activé pour la Fédération : `Get-CsTenantFederationConfiguration` doit afficher `AllowFederatedUsers=true` . <br>-Assurez-vous que la valeur effective de l’utilisateur `CsExternalAccessPolicy` est a `EnableFederationAccess=true` .<br>-Si vous n’utilisez pas la Fédération ouverte, assurez-vous que le domaine cible figure dans `AllowedDomains` de `CsTenantFederationConfiguration` . |
|Locale pure | Dans les outils locaux : <br>-Vérifiez que la Fédération est activée `CsAccessEdgeConfiguration` .<br>-Vérifiez que la Fédération pour l’utilisateur est activée par le biais de `ExternalAccessPolicy` la stratégie globale, de la stratégie de site ou de la stratégie attribuée par l’utilisateur. <br> -Si vous n’utilisez pas la Fédération ouverte, assurez-vous que le domaine cible figure dans la liste `AllowedDomains` . |
|Hybride avec des utilisateurs en ligne (dans Skype entreprise ou Teams) et certains utilisateurs locaux. | Suivez les étapes ci-dessus pour les organisations en ligne et sur site. |

### <a name="delivery-of-incoming-chats-and-calls"></a>Remise de messages et d’appels entrants 

Les conversations et les appels entrants à partir d’un organisme de Fédération débarqueront dans le client teams ou Skype entreprise, en fonction du mode de l’utilisateur destinataire dans TeamsUpgradePolicy.

|**Si vous souhaitez** |**Procédez comme suit :**  |
|:---------|:-----------------------|
| Assurez-vous que les discussions fédérées et les appels entrants arrivent dans le client teams de l’utilisateur : | Configurez vos utilisateurs comme TeamsOnly.
| Assurez-vous que les discussions fédérées et les appels entrants arrivent dans le client Skype entreprise de l’utilisateur | Configurez vos utilisateurs dans un autre mode que TeamsOnly. |


### <a name="enable-federation-between-users-in-your-organization-and-consumer-users-of-skype"></a>Autoriser la Fédération entre les utilisateurs de votre organisation et les utilisateurs de Skype

Pour activer la Fédération entre les utilisateurs de votre organisation et les utilisateurs de Skype :

|**Si votre organisation est** |**Activez la Fédération consommateur comme suit.**  |
|:---------|:-----------------------|
| Une connexion pure sans Skype entreprise locale.  Il s’agit d’organisations incluant des utilisateurs de TeamsOnly et/ou des utilisateurs de Skype entreprise online. | Si vous utilisez le centre d’administration teams : <br>-Assurez-vous que **les utilisateurs peuvent communiquer avec des utilisateurs de Skype** sont activés pour l’accès externe.<br><br>Si vous utilisez PowerShell : <br>-Vérifiez que le client est activé pour la Fédération : `Get-CsTenantFederationConfiguration` doit afficher `AllowPublicUsers=true` . <br> -Assurez-vous que la valeur effective de l’utilisateur `CsExternalAccessPolicy` est a `EnablePublicCloudAccess=true` . |
| Locale pure | Dans les outils locaux : <br> -Vérifiez que Skype est activé en tant que partenaire fédéré. <br> -Assurez-vous que `EnablePublicCloudAccess=true` l’utilisateur passe par le biais d' `ExternalAccessPolicy` une stratégie globale, d’une stratégie de site ou d’une stratégie attribuée par l’utilisateur.|
| Hybride avec des utilisateurs en ligne (dans Skype entreprise ou Teams) et certains utilisateurs locaux.| Suivez les étapes ci-dessus pour les organisations en ligne et sur site.


> [!IMPORTANT]
> Vous n’êtes pas obligé d’ajouter des **domaines Skype** comme domaines autorisés pour permettre aux utilisateurs Teams ou Skype Entreprise Online de communiquer avec des utilisateurs de Skype à l’intérieur ou à l’extérieur de votre organisation. Tous les **domaines Skype** sont des éléments approuvés, ce qui signifie que tous ces domaines sont considérés comme AUTORISÉS.

## <a name="how-does-external-access-compare-with-guest-access"></a>Qu’est-ce que l’accès externe par rapport à l’accès invité ?

Pour en savoir plus sur la différence entre l’accès externe et l’accès invité, consultez [Communiquer avec des utilisateurs d’autres organisations](communicate-with-users-from-other-organizations.md).

## <a name="related-topics"></a>Sujets associés

- [Expérience de conversation native pour les utilisateurs externes (fédérés)](native-chat-for-external-users.md)
