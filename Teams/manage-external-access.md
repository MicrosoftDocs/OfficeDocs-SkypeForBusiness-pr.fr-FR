---
title: Gérez l’accès externe (fédération)
ms.author: mikeplum
author: MikePlumleyMSFT
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
description: Vos équipes ou votre administrateur informatique peuvent configurer un accès externe pour d'autres domaines (fédération) afin de permettre aux utilisateurs de ces domaines de rechercher, d'appeler, de discuter et d'organiser des réunions avec vos utilisateurs.
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: 5a52e479b7dd813af786c33e494675fe7b8e9743
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2022
ms.locfileid: "61766607"
---
# <a name="manage-external-access-in-microsoft-teams"></a>Gérer l’accès externe dans Microsoft Teams

L'accès externe est un moyen pour les utilisateurs de Teams en dehors de votre organisation de rechercher, d'appeler, de discuter et d'organiser des réunions avec vous dans Teams. Vous pouvez également utiliser l’accès externe lorsque vous voulez communiquer avec les membres d’autres organisations qui utilisent encore Skype Entreprise (en ligne ou en local) ou Skype (en version d’évaluation).

Si vous souhaitez que les personnes d'autres organisations aient accès à vos équipes et canaux, utilisez plutôt l'accès invité. Pour plus d’informations sur les différences entre l’accès externe et l’accès invité, voir [Comparer les accès externe et invité](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access). 

Utilisez l’accès externe dans les situations suivantes :
  
- Vous avez des utilisateurs dans des domaines externes qui ont besoin de collaborer. Par exemple, Rob@contoso.com et Ann@northwindtraders.com travaillent sur un projet avec d'autres dans les domaines contoso.com et northwindtraders.com.

- Vous souhaitez que les membres de votre organisation utilisent Teams pour contacter des personnes appartenant à des entreprises spécifiques extérieures à votre organisation.

- Ou vous souhaitez que tous les utilisateurs de Teams à travers le monde puissent vous contacter, à l'aide de votre adresse électronique. 

## <a name="plan-for-external-access"></a>Plan pour l’accès externe

Par défaut, l’accès externe est activé dans Teams, ce qui signifie que votre organisation peut communiquer avec tous les domaines externes. Si vous ajoutez des domaines bloqués, tous les autres domaines sont autorisés. Si vous ajoutez des domaines autorisés, tous les autres domaines sont bloqués. Une exception s’applique si les participants anonymes sont autorisés dans les réunions. Il existe trois scénarios pour configurer l'accès externe dans le centre d'administration Teams (**Utilisateurs** > **Accès externe**) :

> [!NOTE]
> Les utilisateurs de Teams peuvent ajouter des applications lorsqu’ils hébergent des réunions ou des conversations avec des personnes d’autres organisations. Ils peuvent également utiliser des applications partagées par des personnes d’autres organisations lorsqu’ils rejoignent des réunions ou des conversations hébergées par ces organisations. Les stratégies de données de l’organisation de l’utilisateur hôte, ainsi que les pratiques de partage de données de toutes les applications tierces partagées par l’organisation de cet utilisateur, sont appliquées.

> [!NOTE]
> Si vous avez désactiver l’accès externe dans votre organisation, les utilisateurs externes peuvent toujours participer aux réunions via la participation anonyme. Si vous souhaitez en savoir plus, consultez l’article [Gérer les paramètres de réunion dans Teams](meeting-settings-in-teams.md).

- **Autoriser tous les domaines externes** : il s'agit du paramètre par défaut dans Teams, et il permet aux personnes de votre organisation de rechercher, appeler, discuter et organiser des réunions avec des personnes externes à votre organisation dans n'importe quel domaine.

    Dans ce scénario, vos utilisateurs peuvent communiquer avec tous les domaines externes qui exécutent Teams ou Skype Entreprise ou autorisent tous les domaines externes ou ont ajouté votre domaine à leur liste d'autorisation.

- **Autoriser uniquement les domaines externes spécifiques** : En ajoutant des domaines à une liste **Verte**, vous limitez l'accès externe aux seuls domaines autorisés. Une fois que vous avez configuré la liste des domaines autorisés, tous les autres domaines sont bloqués. Pour autoriser certains domaines, cliquez sur **Ajouter un domaine**, ajoutez le nom de domaine, cliquez sur **Action à effectuer sur ce domaine**, puis sélectionnez **Autorisé**.

- **Bloquez des domaines spécifiques**-en ajoutant des domaines à une liste **Bloquer**, vous pouvez communiquer avec tous les domaines externes *à l’exception de* ceux que vous avez bloqués. Pour bloquer certains domaines, cliquez sur **Ajouter un domaine**, ajoutez le nom de domaine, cliquez sur **Action à effectuer sur ce domaine**, puis sélectionnez **Bloqué**. Une fois que vous avez configuré la liste des domaines bloqués, tous les autres domaines sont autorisés.

- **Bloquer tous les domaines externes** – Empêche les personnes de votre organisation de rechercher, d'appeler, de discuter et d'organiser des réunions avec des personnes externes à votre organisation dans n'importe quel domaine.

> [!NOTE]
> Les domaines autorisés ou bloqués s’appliquent uniquement aux réunions si l’accès anonyme aux réunions est désactivé.

## <a name="allow-or-block-domains"></a>Autoriser ou bloquer des domaines

  **Utiliser le centre d’administration Microsoft Teams**

Pour autoriser des domaines spécifiques

1. Dans le centre d'administration Teams, accédez à **Utilisateurs** > **Accès externe**.

2. Sous **Choisir les domaines auxquels vos utilisateurs ont accès**, choisissez **Autoriser uniquement les domaines externes spécifiques**.

3. Sélectionnez **Autoriser les domaines**.

4. Dans la zone **Domaine**, tapez le domaine que vous souhaitez autoriser, puis cliquez sur **Terminé**.

5. Si vous souhaitez autoriser un autre domaine, cliquez sur **Ajouter un domaine**.

6. Cliquez sur **Enregistrer**.

Pour bloquer des domaines spécifiques

1. Dans le centre d'administration Teams, accédez à **Utilisateurs** > **Accès externe**.

2. Sous **Choisir les domaines auxquels vos utilisateurs ont accès**, choisissez **Bloquer uniquement les domaines externes spécifiques**.

3. Sélectionnez **Bloquer les domaines**.

4. Dans la zone **Domaine**, tapez le domaine que vous souhaitez autoriser, puis cliquez sur **Terminé**.

5. Si vous souhaitez bloquer un autre domaine, cliquez sur **Ajouter un domaine**.

6. Cliquez sur **Enregistrer**.

Assurez-vous que l'administrateur de l'autre organisation Teams effectue ces mêmes étapes. Par exemple, dans leur liste de **domaines autorisés**, leur administrateur doit saisir le domaine de votre entreprise s'il limite les organisations pouvant communiquer avec leurs utilisateurs.

## <a name="communicate-with-skype-users-preview"></a>Communiquer avec les utilisateurs de Skype (préversion)

Pour permettre aux membres Teams de votre organisation de discuter avec et d’appeler des utilisateurs de Skype, procédez comme suit. Les membres de Teams peuvent ensuite rechercher et démarrer une conversation texte privée ou un appel audio/vidéo avec des utilisateurs de Skype, et vice-versa.

  **Utiliser le centre d’administration Microsoft Teams**

1. Dans la navigation de gauche, accédez à **Utilisateurs** > **Accès externe**.

2. Activez le paramètre **Autoriser les utilisateurs de mon organisation à communiquer avec les utilisateurs Skype**.

Pour en savoir plus sur la manière dont les utilisateurs de Teams et les utilisateurs de Skype peuvent communiquer, y compris les limitations qui s’appliquent, voir [Interopérabilité Skype et Teams](teams-skype-interop.md).

## <a name="block-unsolicited-contact-with-external-unmanaged-teams-users"></a>Bloquer les contacts non sollicités avec des utilisateurs externes non Teams

Pour empêcher les utilisateurs de votre Teams contact non sollicité avec des utilisateurs Teams externes dont les comptes ne sont pas gérés par une organisation, suivez ces étapes.

  **Utiliser le centre d’administration Microsoft Teams**

1. Dans la navigation de gauche, accédez à **Utilisateurs** > **Accès externe**.

2. Suivez l’une des étapes suivantes :

    - Pour empêcher les utilisateurs Teams de votre organisation de communiquer avec des utilisateurs Teams externes dont les comptes ne sont pas gérés par une organisation, désactiver les personnes de mon organisation peuvent communiquer avec des Teams utilisateurs dont les comptes ne sont pas gérés par un paramètre **d’organisation** et effacer les utilisateurs externes avec des comptes Teams non gérés par une organisation peuvent contacter les utilisateurs de mon **organisation case** à cocher Contrôle.

    - Pour que les utilisateurs de Teams de votre organisation communiquent avec des utilisateurs de Teams externes dont les comptes ne sont pas gérés par une organisation si vos utilisateurs Teams ont commencé le contact, activer les personnes de mon organisation peuvent communiquer avec des utilisateurs Teams dont les comptes ne sont pas gérés par un paramètre **d’organisation** et effacer les utilisateurs externes avec des comptes **Teams  non gérée par une organisation ne peut contacter les utilisateurs dans la case à cocher de mon** organisation.

    - Pour que les utilisateurs de Teams de votre organisation communiquent avec des utilisateurs de **Teams externes dont les comptes ne sont pas gérés par une organisation et reçoivent des demandes de communication avec ces** utilisateurs Teams **externes,** activer La fonction Personnes de mon organisation peut communiquer avec les utilisateurs de Teams dont les comptes ne sont pas gérés par un paramètre de l’organisation et sélectionner les utilisateurs externes dont les comptes Teams ne sont pas gérés par une organisation peut contacter les utilisateurs de mon organisation.

## <a name="test-access"></a>Tester l’accès

Pour tester votre configuration, vous devez disposer d’un contact Teams qui ne soit pas derrière votre pare-feu.
  
1. Une fois que vous et l’administrateur de l’organisation avez modifié les paramètres d’**Accès externe**, vous devriez être prêt.

2. Dans l’application Teams, recherchez la personne par adresse de messagerie et envoyez une demande de conversation.

3. Demandez à votre contact Teams de vous envoyer une demande de discussion. Si vous ne la recevez pas, le problème se situe au niveau de vos paramètres de pare-feu (en supposant que votre contact a confirmé que ses paramètres sont corrects).

4. Une autre méthode pour tester si le problème est lié à votre pare-feu consiste à utiliser un emplacement WiFi non protégé par votre pare-feu. par exemple, un cybercafé, et vous pouvez utiliser Teams pour envoyer une demande de conversation à votre contact. Si le message a pu être envoyé depuis l’emplacement WiFi et non depuis votre bureau, vous savez alors que le problème est lié à votre pare-feu.

> [!NOTE]
> Si vous et un autre utilisateur activez l’accès externe et autorisez les domaines d’un autre utilisateur, cela fonctionnera. Si cela ne fonctionne pas, l’autre utilisateur doit s’assurer que sa configuration ne bloque pas votre domaine.

## <a name="limit-external-access-to-specific-people"></a>Limiter l’accès externe à des personnes spécifiques

Si vous avez activé **Les personnes de mon organisation peuvent communiquer avec des Teams utilisateurs dont les comptes ne sont pas gérés par un paramètre d’organisation**, vous pouvez limiter l’accès externe à des membres spécifiques à l’aide de PowerShell.

Vous pouvez utiliser l’exemple de script ci-dessous, en remplaçant *PolicyName* par le nom que vous voulez donner à la stratégie, et *UserName* pour chaque utilisateur que vous voulez pouvoir utiliser l’accès externe.

Assurez-vous d’avoir installé le module PowerShell [Microsoft Teams](/microsoftteams/teams-powershell-install) avant d’exécuter le script.

```PowerShell
Connect-MicrosoftTeams

# Disable external access globally
Set-CsExternalAccessPolicy -EnableTeamsConsumerAccess $false

# Create a new external access policy
New-CsExternalAccessPolicy -Identity <PolicyName> -EnableTeamsConsumerAccess $true

# Assign users to the policy
$users_ids = @("<UserName1>", "<UserName2>")
New-CsBatchPolicyAssignmentOperation -PolicyType ExternalAccessPolicy -PolicyName "<PolicyName>" -Identity $users_ids

```

Par exemple :

```PowerShell
Connect-MicrosoftTeams

Set-CsExternalAccessPolicy -EnableTeamsConsumerAccess $false

New-CsExternalAccessPolicy -Identity ContosoExternalAccess -EnableTeamsConsumerAccess $true

$users_ids = @("MeganB@contoso.com", "AlexW@contoso.com")
New-CsBatchPolicyAssignmentOperation -PolicyType ExternalAccessPolicy -PolicyName "ContosoExternalAccess" -Identity $users_ids

```

Consultez [ New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) pour obtenir des exemples supplémentaires de compilation d’une liste d’utilisateurs.

Vous pouvez voir la nouvelle stratégie en exécutant `Get-CsExternalAccessPolicy`.


Voir également [New-CsExternalAccessPolicy](/powershell/module/skype/new-csexternalaccesspolicy) et [Set-CsExternalAccessPolicy.](/powershell/module/skype/set-csexternalaccesspolicy)

## <a name="common-external-access-scenarios"></a>Scénarios d’accès externe courants

Les sections suivantes décrivent comment activer la fédération pour les scénarios d’accès externe courants, et comment TeamsUpgradePolicy détermine la remise des conversations et appels entrants.

### <a name="enable-federation"></a>Activer la fédération

Pour permettre aux utilisateurs de votre organisation de communiquer avec des utilisateurs d’une autre organisation, les deux organisations doivent activer la fédération. Les étapes à suivre pour activer la fédération pour une organisation donnée varient selon que l’organisation est uniquement en ligne, hybride ou uniquement en local.

| Si votre organisation | Activer la fédération comme suit |
|:---------|:-----------------------|
|En ligne sans Skype Entreprise en local. Cela inclut les organisations qui ont des utilisateurs de TeamsOnly et/ou Skype Entreprise Online.| Si vous utilisez le Centre d’administration Teams : <br>- Assurez-vous que les domaines avec lesquels vous souhaitez communiquer sont autorisés dans l'accès externe.<br><br>Si vous utilisez PowerShell :<br>- Vérifiez que le client est activé pour la fédération : `Get-CsTenantFederationConfiguration` doit afficher `AllowFederatedUsers=true`. <br>- Assurez-vous que la valeur effective de l’utilisateur `CsExternalAccessPolicy` est de `EnableFederationAccess=true`.<br>- Si vous n’utilisez pas la fédération ouverte, assurez-vous que le domaine cible est répertorié dans `AllowedDomains` de `CsTenantFederationConfiguration`. |
|Local pur | Dans les outils locaux : <br>- Vérifiez que la fédération est activée dans `CsAccessEdgeConfiguration`.<br>- Vérifiez que la fédération de l’utilisateur est activée via `ExternalAccessPolicy` (soit la stratégie globale, la stratégie de site ou la stratégie attribuée par l’utilisateur). <br> - Si vous n’utilisez pas la fédération ouverte, assurez-vous que le domaine cible est répertorié dans `AllowedDomains`. |
|Hybride avec certains utilisateurs en ligne (dans Skype Entreprise ou Teams) et certains utilisateurs en local. | Suivez les étapes ci-dessus pour les organisations en ligne et locales. |

### <a name="delivery-of-incoming-chats-and-calls"></a>Remise de conversations et d’appels entrants 

Les conversations et appels entrants d’une organisation de fédération arrivent dans le client Teams ou Skype Entreprise de l’utilisateur, en fonction du mode utilisé par l’utilisateur destinataire dans TeamsUpgradePolicy.

| Si vous voulez | Procédez comme suit : |
|:---------|:-----------------------|
| Vérifiez que les conversations et appels fédérés entrants arrivent dans le client Teams de l’utilisateur : | Configurez vos utilisateurs de façon à ce qu’ils utilisent TeamsOnly.
| Vérifiez que les conversations et appels fédérés entrants arrivent dans le client Skype Entreprise de l’utilisateur | Configurez vos utilisateurs pour qu’ils utilisent un mode autre que TeamsOnly. |


### <a name="enable-federation-between-users-in-your-organization-and-consumer-users-of-skype"></a>Activez la fédération entre les utilisateurs de votre organisation et les utilisateurs grand public de Skype

Pour activer la fédération entre les utilisateurs de votre organisation et les utilisateurs grand public de Skype :

| Si votre organisation | Activez la fédération des consommateurs comme suit : |
|:---------|:-----------------------|
| En ligne pur, sans Skype Entreprise en local.  Cela inclut les organisations qui ont des utilisateurs de TeamsOnly et/ou Skype Entreprise Online. | Si vous utilisez le Centre d’administration Teams : <br>-Assurez-vous que **Autoriser les utilisateurs de mon organisation à communiquer avec les utilisateurs Skype** est activé dans l'accès externe.<br><br>Si vous utilisez PowerShell : <br>- Vérifiez que le client est activé pour la fédération : `Get-CsTenantFederationConfiguration` doit afficher `AllowPublicUsers=true`. <br> - Assurez-vous que la valeur effective de l’utilisateur `CsExternalAccessPolicy` est de `EnablePublicCloudAccess=true`. |
| Local pur | Dans les outils locaux : <br> - Assurez-vous que Skype est activé en tant que partenaire fédéré. <br> - Vérifiez que `EnablePublicCloudAccess=true` pour l’utilisateur via `ExternalAccessPolicy` (via une stratégie globale, une stratégie de site ou une stratégie attribuée par l’utilisateur).|
| Hybride avec certains utilisateurs en ligne (dans Skype Entreprise ou Teams) et certains utilisateurs en local.| Suivez les étapes ci-dessus pour les organisations en ligne et locales.


> [!IMPORTANT]
> Vous n'avez pas besoin d'ajouter de **domaines Skype** en tant que domaines autorisés pour permettre aux utilisateurs Teams ou Skype Entreprise Online de communiquer avec les utilisateurs Skype à l'intérieur ou à l'extérieur de votre organisation. Tous les **domaines Skype** sont autorisés.

## <a name="federation-diagnostic-tool"></a>Outil de diagnostic de fédération

Si vous êtes administrateur, vous pouvez utiliser l'outil de diagnostic suivant pour valider qu'un utilisateur Teams peut communiquer avec un utilisateur Teams fédéré :

1. Sélectionnez **Exécuter les tests** ci-dessous, qui remplira le diagnostic dans le Centre d'Administration Microsoft 365. 

   > [!div class="nextstepaction"]
   > [Exécuter des tests : fédération d'équipes](https://aka.ms/TeamsFederationDiag)

2. Dans le volet Exécuter le diagnostic, saisissez **l'adresse SIP (Session Initiation Protocol)** et le **nom de domaine du locataire fédéré**, puis sélectionnez **Exécuter les tests**.

3. Les tests renverront les meilleures prochaines étapes pour traiter les configurations de locataire ou de stratégie qui empêchent la communication avec l'utilisateur fédéré.


## <a name="related-topics"></a>Sujets associés

- [Expérience de conversation native pour les utilisateurs externes (fédérés)](native-chat-for-external-users.md)
