---
title: Connecter Microsoft Teams Essentials (AAD identité) vers un système de courrier existant avec le calendrier
author: adjoseph
ms.author: adjoseph
ms.reviewer: jimmyw
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: Découvrez comment connecter Microsoft Teams Essentials (AAD Identity) à un système de courrier existant avec un calendrier tel que Google Workspace
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3b05fb30b6e7e4a3f3725ca8e591cc5caf56fdde
ms.sourcegitcommit: 909b0a709983d21fa6f2b547a78cc6a1222188df
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/30/2022
ms.locfileid: "62279242"
---
# <a name="connect-microsoft-teams-essentials-aad-identity-to-an-existing-email-system-with-calendar"></a>Connecter Microsoft Teams Essentials (AAD identité) vers un système de courrier existant avec le calendrier

Ce guide fournit les étapes de configuration pour connecter Microsoft Teams Essentials (AAD Identity) à un système de courrier existant avec le calendrier.

Microsoft Teams Essentials (AAD identité) réunit le meilleur de Teams avec les réunions, les discussions, les appels et la collaboration. Teams Essentials (identité AAD) peut se connecter à votre système de courrier existant pour offrir une expérience intégrée, telle que la réception de toutes les notifications Teams dans une boîte aux lettres existante, tous les événements de calendrier dans Teams et la possibilité de se connecter à Teams avec votre adresse de messagerie existante.

Une fois la connexion connectée, vous pouvez voir les réponses aux réunions programmées et aux invitations pour collaborer dans votre boîte aux lettres et Microsoft Teams. Vous pouvez également afficher et interagir avec les réunions entrantes à partir de votre calendrier à l’aide d Teams logiciels de réunion tiers tels que Google Workspace.

## <a name="prerequisites"></a>Conditions préalables

Les étapes de configuration de cet article impliquent le processus de forwardage automatique des éléments à partir Exchange Online. Par défaut, le forwardage automatique est désactivé par la stratégie sortante anti-courrier indésirable. Cette stratégie doit être activée pour la connexion de Teams Essentials à un système de boîte aux lettres et de calendrier existant.

Pour activer le forwardage automatique :

1. Allez sur le portail Microsoft 365 Defender de l’entreprise à<https://security.microsoft.com/>
2. Sous le menu de navigation de gauche, allez à **Email &** **collaborationPolicies** >  & **Reat** **policiesAnti-spam** >  >  dans la section Stratégies
3. Sur la page **Stratégies anti-courrier** indésirable, sélectionnez Stratégie sortante **anti-courrier indésirable (** par défaut) dans la liste
4. Dans le volant des détails de la stratégie qui s’affiche, sélectionnez Modifier les **paramètres de protection** pour modifier la règle d’forwarding automatique.
5. Sous **Règles de forwardage**, activez la condition de forwardage automatique pour activer le forwarding **et** enregistrez vos modifications.

:::image type="content" source="media/essentials-antispam.png" alt-text="Image montrant le survol de la stratégie sortante anti-courrier indésirable du portail Microsoft Defender avec activé, la condition de forwardage est activée sous les règles de forwarding." :::

Pour en savoir plus sur la configuration des stratégies de courrier indésirable sortant, consultez Configurer le filtrage du courrier [indésirable sortant - Office 365 | Microsoft Docs](/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide&preserve-view=true).

## <a name="connect-teams-essentials-to-exchange-online-with-exchange-on-premises"></a>Connecter Teams Essentials pour Exchange Online avec Exchange local

Vous pouvez profiter de tout ce que Teams Essentials (AAD) a à offrir en utilisant une approche hybride pour configurer la connexion entre Microsoft Teams et Exchange Online avec Exchange en local.

Pour que l’accès au calendrier fonctionne pour vos boîtes aux lettres locaux, suivez les instructions fournies lors de la configuration de l’accès au calendrier Teams pour les boîtes aux lettres Exchange sur site [- Microsoft Tech Community](https://techcommunity.microsoft.com/t5/exchange-team-blog/configuring-teams-calendar-access-for-exchange-on-premises/ba-p/1484009)

Pour déployer des Salles Microsoft Teams dans un environnement hybride avec Exchange en local, visitez la Salles Microsoft Teams Déploiement avec Exchange en local [- Microsoft Teams | Microsoft Docs](rooms/with-exchange-on-premises.md)

## <a name="connect-teams-essentials-to-third-party-email-systems-with-calendar"></a>Connecter Teams Essentials aux systèmes de courrier tiers avec calendrier

Si vous ne prévoyez pas de basculer la boîte aux lettres de votre organisation vers Microsoft 365, vous pouvez connecter Teams Essentials à un système de courrier électronique et de calendrier tiers existant. Cette connexion vous permet de recevoir des notifications Teams dans votre système de courrier existant tout en visionnage des invitations aux réunions et des événements de calendrier existants dans Microsoft Teams.

### <a name="connect-teams-essentials-to-third-party-email-using-vanity-domain-google-workspace-example"></a>Connecter Teams Essentials à la messagerie tierce à l’aide d’un domaine vanity (exemple Google Workspace)

La section suivante vous montre comment vous connecter Microsoft Teams un système de courrier existant avec le calendrier, tel que Google Workspace. Vous allez accomplir cette connexion en laissant le système de courrier actuel intact, en forwardant tous les messages électroniques vers Exchange Online, en filtrant tout, à l’exception des messages électroniques du type de calendrier. Ainsi, les messages de calendrier apparaissent automatiquement dans le calendrier Teams les courriers acceptés comme courriers de type provisoire et non calendaire sont supprimés.

Tous les messages électroniques générés dans Microsoft 365 sont transmis à Google Workspace afin que les utilisateurs Teams les rappels et notifications. Les identités des utilisateurs, telles que l’adresse de courrier principale de l’utilisateur, peuvent être dupliquées. L’sign-on unique est également possible, mais pas obligatoire. Les utilisateurs doivent être en mesure de participer Teams réunions à partir du calendrier tiers ou à partir Teams calendrier. Une Teams fonctionnalités supplémentaires fonctionneront comme prévu.

:::image type="content" source="media/essentials-googleworkspace.png" alt-text="Image illustrant un diagramme du flux de courrier entre EXO et Gmail":::

Ces exemples [s’appuient sur l’Connecter commande PowerShell Connecter-ExchangeOnline](/powershell/module/exchange/connect-exchangeonline?view=exchange-ps&preserve-view=true) qui fait partie du [module Exchange Online PowerShell V2](/powershell/exchange/exchange-online-powershell-v2&preserve-view=true). Si vous obtenez une erreur lors de l’exécution de Connecter-ExchangeOnline, assurez-vous de suivre les instructions recommandées pour l’installation du module à l’aide du [module EXO V2](/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps&preserve-view=true). Lorsque Connect-ExchangeOnline vous invitez à utiliser des informations d’identification, assurez-vous d’utiliser un compte d’administrateur client.

**Étape 1 : configurer un nouveau domaine Microsoft 365 client**

1. Pour ce faire, vous allez au Centre d’administration à l’adresse <https://admin.microsoft.com>.

2. Allez à **Set** **UpDomains** >  et **sélectionnez Ajouter un domaine** pour ajouter votre domaine existant. Si vous n’ajoutez pas de domaine, les membres de votre organisation utiliseront le domaine onmicrosoft.com pour leur adresse de messagerie jusqu’à ce que vous le faisiez. Veillez à ajouter votre domaine avant d’ajouter des utilisateurs, de sorte que vous n’avez pas à les configurer deux fois.

3. Vérifiez le domaine avec un enregistrement TXT en suivant les étapes de la procédure Vérifier [avec un enregistrement TXT](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider?view=o365-worldwide&preserve-view=true).

4. À l’invite, **sélectionnez Ne pas Microsoft 365 configurer DNS**.

5. À l’invite, laissez les enregistrements MX existants en place sans les modifier.

6. Mettez à jour l’enregistrement TXT SPF existant de Microsoft 365.

7. Configurez DKIM (DomainKeys Identified Mail) pour les Microsoft 365 en suivant ces étapes pour configurer manuellement [la messagerie DKIM](/microsoft-365/security/office-365-security/use-dkim-to-validate-outbound-email?view=o365-worldwide&preserve-view=true).

8. Sign back into the Centre d'administration Microsoft 365 at <https://admin.microsoft.com/AdminPortal/> to enable DKIM

9. Dans le panneau de navigation sur la gauche, sélectionnez **SetupDomains**  > 

10. À l’aide de la case à cocher, sélectionnez votre domaine non-Microsoft existant (par exemple , TomislavK@thephone-company.com) dans les listes de domaines actuelles.

11. Sélectionnez le bouton avec **trois points verticaux** pour ouvrir un menu.

12. Dans le menu, sélectionnez **Définir par défaut**

13. **Confirmez l’option définie** par défaut dans la fenêtre qui apparaît pour définir votre domaine existant comme domaine par défaut.
    :::image type="content" source="media/essentials-internalrelay2.png" alt-text="Image de la boîte de dialogue de confirmation de la définition du domaine par défaut":::

    Pour obtenir des instructions supplémentaires sur l’ajout d’un domaine Microsoft 365 domaine, suivez les étapes décrites dans [Ajouter un domaine Microsoft 365](https://support.office.com/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US).

**Étape 2 : ajouter des utilisateurs et Teams licences Essentials**

1. Pour ajouter un utilisateur individuel, rendez-vous dans le Centre <https://admin.microsoft.com> d’administration

2. Go to **UsersActive** >  **users**, and select **Add a user**

3. Dans le **volet Configurer le base** , remplissez les informations de base de l’utilisateur, puis sélectionnez **Suivant**.
    - **Nom :** Remplissez le prénom et le nom, le nom d’affichage et le nom d’utilisateur.
    - **Domaine :** Sélectionnez le domaine du compte d’utilisateur. Par exemple, si le nom d’utilisateur est Jakob et que le domaine est contoso.com, il se connecte à l’aide de jakob@contoso.com.
    - **Paramètres de mot de passe :** Choisissez d’utiliser le mot de passe créé automatiquement ou de créer votre propre mot de passe fort pour l’utilisateur.  Déterminez si vous voulez envoyer le mot de passe dans un message électronique lorsque l’utilisateur est ajouté.

4. Dans le **volet Attribuer des licences de** produits, sélectionnez l’emplacement et la licence appropriée pour l’utilisateur. Si vous n’avez pas de licences disponibles, vous pouvez toujours ajouter un utilisateur et en acheter d’autres. Sélectionnez Suivant.

5. Dans le **volet Paramètres facultatifs** , développez **Rôles** si vous souhaitez faire de cet utilisateur un administrateur. **Développez les informations de profil** pour ajouter des informations supplémentaires sur l’utilisateur.

6. **Sélectionnez** Suivant, examinez les paramètres de votre nouvel utilisateur, apportant d’autres modifications si nécessaire, sélectionnez Terminer l’ajout **, puis** fermez.

Pour ajouter plusieurs utilisateurs en même temps, suivez les étapes recommandées de la page Ajouter des [utilisateurs et attribuer des licences - En savoir Microsoft 365'| Microsoft Docs](/microsoft-365/admin/add-users/add-users?view=o365-worldwide&preserve-view=true)

**Étape 3 : configurer Google Workspace**

***Configurez la remise en double des messages Microsoft 365 les pièces jointes :***

1. Suivez les étapes de Google pour la configuration de la livraison double : <https://support.google.com/a/answer/9228551?hl=en>

2. Ajouter un itinéraire pour une Office 365

    - Allez sur la console d’administration de Google à l’adresse <https://admin.google.com>)
    - Accéder à Applications > Google Workspace > Gmail > Hosts.
    - Entrez un nom d’itinéraire. (Par exemple, Microsoft 365)
    - Sélectionnez « Hôte unique » et entrez l’enregistrement MX spécifié pour le domaine dans Microsoft 365 (par exemple : ContosoLandscaping2-m365master-com.mail.protection.outlook.com)

    **Méthode hôte intelligente pour résoudre le code de réponse ATTR35 lorsque le courrier est envoyé à un Exchange local/Exchange Online :**
    - Sélectionnez « Hôte unique » et entrez l’enregistrement MX du domaine initial du client en tant qu’hôte intelligent. Le domaine initial est au format GUID.onmicrosoft.com. Un GUID est une valeur unique fournie à chaque organisation dans le cadre de son inscription au service. Un GUID est un ensemble de 128 bits (16 octets) qui peut être utilisé sur tous les ordinateurs et réseaux où un identificateur unique est requis.
    - Vous pouvez utiliser la ligne de commande : Nslookup -type MX GUID.onmicrosoft.com pour résoudre l’enregistrement MX (par exemple : contosolandscaping2.mail.protection.outlook.com)
    - **Sélectionnez Port:25**
    - Poursuivre avec les options recommandées

3. Configurer l’itinéraire vers Office 365

    - Ouvrez la **console d’administration de Google** sur <https://admin.google.com>

    - Go to **AppsGoogle** >  **WorkspaceGmailRouting** >  > 

    - Sous **l’onglet Routage** , **sélectionnez Configurer**

    - Entrez **le nom** de la règle. (Par exemple, Gmail à Office 365)

    - Pour **que les messages électroniques affectent**, sélectionnez **à la fois** Entrant et  **Interne.**

    - Sous **Pour les types de messages ci-dessus**, **sélectionnez Modifier le message**

    - Sous **Envoyer à également**, **sélectionnez Ajouter d’autres destinataires** , puis **sélectionnez Ajouter pour ajouter l’itinéraire de courrier secondaire.**

    - Sous **Destinataires**, sélectionnez la flèche vers le bas « », puis **Sélectionnez Avancé.**

    - **Sélectionnez Modifier l’itinéraire.**

    - Dans la liste, sélectionnez l’itinéraire de courrier secondaire que vous avez créé précédemment.

    - Sous **Pièces jointes**, **sélectionnez Supprimer les pièces jointes du message**

    - Faites défiler vers le bas et **sélectionnez Enregistrer**.

***Ajoutez votre sous-domaine dans Google Workspace pour recevoir les messages Microsoft 365.***

  Vous devez ensuite créer des règles de Microsoft 365 boîtes aux lettres vers votre sous-domaine. Choisissez un sous-domaine à utiliser dans Google Workspace pour recevoir les messages Microsoft 365 (par exemple, g.contosolandscaping2.m365master.com)

1. Démarrer sur **la console d’administration de Google** (admin.google.com)

2. Go to **AccountDomainsManage** >  >  **Domains**

3. **Sélectionnez Ajouter un domaine**

4. Entrer le nom de domaine que vous avez sélectionné

5. Sélectionner un **domaine d’alias d’utilisateur**

6. **Sélectionnez Ajouter un domaine & commencer la vérification**

7. Attendre la vérification pour terminer et actualiser la page

8. Sélectionnez **Activer Gmail**

9. **Sélectionnez Ignorer la configuration d’un enregistrement MX**, puis **SUIVANT**

10. Dans la **boîte** de dialogue Router le courrier vers un autre serveur, notez le serveur vers qui router le courrier (par exemple, aspmx.l.google.com), puis sélectionnez J’utilise un **autre serveur de courrier.**

***Autoriser le courrier électronique en provenance Microsoft 365 à contourner le filtre ANTI-COURRIER indésirable***

1. Recherchez un en-tête approprié à partir Microsoft 365 client en envoyant un courrier électronique à un utilisateur sur Google Workspace.

2. Ouvrez le message et sélectionnez **Afficher l’original.**

3. Choisissez un en-tête de courrier qui identifie de façon unique les messages provenant de Microsoft 365 client. (Par exemple, X-MS-Exchange-CrossTenant-id : 92f60fc7-eab3-403b-9d7d-9d683bf0a4b5)

4. Sur la **console d’administration de Google** , à l’adresse <https://admin.google.com>

5. Go to **AppsGoogle** >  **WorkspaceGmailCompliance** >  > 

6. Accédez à **Conformité du contenu** , puis **sélectionnez Configurer**

7. Donnez un nom au paramètre. Par exemple, Liste d’adresses Microsoft 365 courrier électronique.

8. Sous les **messages électroniques pour affecter la** vérification entrante

9. Sous **Ajouter des expressions qui décrivent le contenu que vous souhaitez rechercher dans chaque message** , sélectionnez si l’une des expressions **suivantes correspond au message**

10. Sous **Expressions**, **sélectionnez Ajouter** xi. Sous **Paramètre Ajouter**, sélectionnez **Correspondance de contenu avancé**

11. Sous **Emplacement,** **sélectionnez En-têtes complets**

12. Sous **Type de correspondance** , **sélectionnez Texte intégral**

13. Sous le contenu, entrez l’en-tête d’e-mail qui identifie de manière unique le courrier électronique provenant de votre client Microsoft 365 (par exemple, X-MS-Exchange-CrossTenant-id : 92f60fc7-eab3-403b-9d7d-9d683bf0a4b5)

14. Sélectionnez **Enregistrer**

15. Dans la **zone Si les expressions ci-dessus correspondent,** dans le champ > **modifier le message** , puis vérifiez que le filtre anti-courrier indésirable de ce **message est** contourné sous **Courrier indésirable**.

16. Sélectionnez **Enregistrer**

**Étape 4 : configurer les Microsoft 365 de l’intégration**

*Configurer un connecteur pour router le courrier à partir Microsoft 365 vers Gmail :*

1. Dans le Centre **d’administration Microsoft, à** l’adresse <https://admin.microsoft.com/AdminPortal>

2. **Sélectionnez Afficher tout** dans le menu de navigation gauche.

3. Sous **Centres d’administration**, **Exchange** sélectionnez pour ouvrir Exchange centre d’administration dans un nouvel onglet

4. Dans **le Exchange** navigation gauche du Centre d’administration, sélectionnez **Mail** **flowConnectors** > , ouvrez le menu overflow (...) et sélectionnez Ajouter un connecteur

5. Sous **Connexion à partir** de la fenêtre Nouveau connecteur, **sélectionnez Office 365**

6. Sous **Connexion pour** sélectionner le serveur de courrier de votre organisation, sélectionnez **Suivant**

7. Entrez un **nom** pour le nouveau connecteur (Par exemple : vers Gmail) et continuez **Suivant**

8. Dans la section **Utilisation du connecteur** , sélectionnez Uniquement lorsque j’ai une règle de transport définie qui redirige les **messages vers ce** connecteur, puis **sélectionnez Suivant**.

9. Dans la section Routage, entrez l’hôte de courrier intelligent approprié (par exemple, aspmx.l.google.com), **+** sélectionnez, puis continuez **Suivant**.

10. Dans la section **Restrictions de sécurité** , acceptez les paramètres par défaut en sélectionnant **Suivant**

11. Dans la **section Validation du courrier**, entrez une adresse e-mail valide pour le système Gmail (par exemple, johannal@g.contosolandscaping2.m365master.com), sélectionnez le signe **plus (+),** puis sélectionnez **Valider**

12. Attendez la validation et, si le succès est terminé, appuyez sur Suivant

13. Sous **Connecteur Révision, vérifiez** que la configuration est correcte, puis appuyez sur Créer un connecteur

14. Lorsque vous voyez la notification de création de connecteur, appuyez sur **Terminé**

*Forward mail from Microsoft 365 mailboxes to Gmail*

1. Utilisez le **Administration Microsoft 365 Center pour** mettre à jour chaque boîte aux lettres ou vous pouvez utiliser un script **PowerShell**, comme suit :

    ```powershell
    $forwardingDomain = "g.contosolandscaping2.m365master.com"
    Connect-ExchangeOnline
    $Mailboxes = Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"}
    Foreach ($mbx in $mailboxes) {
    
    Set-Mailbox $mbx.Identity -DeliverToMailboxAndForward $true -ForwardingSMTPAddress $($mbx.Alias,$forwardingDomain -join "@")
    } 
    ```

    **Résolution des problèmes Connecter-ExchangeOnline :**

    Vous rencontrez une erreur lors de l’exécution Connecter-ExchangeOnline ? Cela peut être le résultat de la règle de forwardage automatique du courrier électronique de votre organisation. Par défaut, le forwarding automatique est désactivé. Pour connecter Teams Essentials à Google Workspace, la règle doit être activée.  

    Entrez le script suivant :

   ```powershell
    Set-ExecutionPolicy Unrestricted 
     ```

    Ensuite, exécutez les commandes suivantes :

    ```powershell
    Enable-OrganizationCustomization 
    Get-HostOutboundSpamFilterPolicy | set-HostedOutboundSpamFilterPolicy -AutoForwardingMode On
    ```

*Configurer une Exchange Online transport directe vers le calendrier*

1. La configuration de ce paramètre accepte automatiquement les invitations de calendrier afin qu’elles s’affichent dans le calendrier Teams sans exiger que les utilisateurs interagissent avec l’invitation dans Outlook Web App.

2. Le script suivant peut être utilisé pour créer les règles de transport :

    ```powershell
    Connect-ExchangeOnline
    New-TransportRule -Name "Direct to Calendar" -MessageTypeMatches Calendaring -SetHeaderName "X-MS-Exchange-Organization-CalendarBooking-Response" -SetHeaderValue Tentative
    New-TransportRule -Name "Direct to Calendar triage action" -MessageTypeMatches Calendaring -SetHeaderName "X-MS-Exchange-Organization-CalendarBooking-TriageAction" -SetHeaderValue MoveToDeletedItems
    
    ```

*Désactiver le Outlook sur le web pour les boîtes aux lettres*

1. Suivez les instructions de [la](/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app) boîte aux lettres Activez ou désactivez Outlook sur le web boîte aux lettres dans Exchange Online pour désactiver Outlook sur le web pour les boîtes aux lettres.

2. Vous pouvez désactiver les Outlook sur le web à l’aide **Exchange Centre d’administration ou** **PowerShell**. Vous pouvez utiliser l’exemple PowerShell suivant pour désactiver Outlook sur le web pour toutes les boîtes aux lettres :

    ```powershell
    Connect-ExchangeOnline
    $Mailboxes = Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"}
    Foreach ($mbx in $mailboxes) {
    Set-CASMailbox $mbx.Identity -OWAEnabled $false
    }
    ```

**Étape 5 : configurer Exchange Online domaine pour le relais interne**

Cette étape permet de s’assurer que le courrier électronique est envoyé à un système tiers pour la résolution finale.

1. Dans le Centre **d’administration Microsoft, à** l’adresse <https://admin.microsoft.com/AdminPortal>

2. Dans la navigation à gauche, sélectionnez **Afficher tout**

3. Sous **Centres d’administration**, **sélectionnez Exchange** pour ouvrir Exchange centre d’administration dans un nouvel onglet

4. Dans **Exchange d’administration**, sélectionnez **Flux** de courrier dans le menu de navigation gauche, puis sélectionnez **Domaines acceptés**

5. Appuyez sur le nom de domaine configuré dans le système tiers (par exemple, contosoLandscaping2.m365master.com)

    :::image type="content" source="media/essentials-internalrelay1.png" alt-text="Image montrant les paramètres Exchange centre d’administration pour le flux de courrier.":::

6. Sélectionnez **Relais interne**, puis cliquez sur **Enregistrer**

    :::image type="content" source="media/essentials-internalrelay2.png" alt-text="Image montrant l’enregistrement d’un paramètre de relais interne.":::

**Étape 6 : créer une règle pour supprimer tous les messages entrants envoyés à Exchange Online à l’exception du calendrier**

1. Vous pouvez configurer cette règle dans le Exchange **d’administration ou** **PowerShell**. Vous pouvez utiliser l’exemple **PowerShell** suivant pour créer la règle :

    ```powershell
    Connect-ExchangeOnline
    New-TransportRule -Name "Delete all except Calendaring" -ExceptIfMessageTypeMatches Calendaring -FromScope NotInOrganization -DeleteMessage:$true 
    
    ```

### <a name="connect-teams-essentials-to-third-party-email-not-using-vanity-domain-gmail-example"></a>Connecter Teams Essentials à la messagerie tierce n’utilisant pas de domaine personnel (exemple Gmail)

Vous pouvez planifier et participer à une réunion Teams directement à partir de Google Workspace en connectant un compte Gmail grand public à Teams Essentials, en ayant essentiellement besoin du module Teams [G Suite](https://support.microsoft.com/en-us/office/install-the-teams-meeting-add-on-for-google-workspace-bba2dfbe-0b2b-4ee7-be10-261ad80ddb60). Vous avez ainsi la possibilité de planifier des vidéoconférences et des audioconférences avec partage d’écran, conversation de réunion, tableaux blancs numériques, etc.

Vous configurerez Gmail de manière à ce qu’il en sorte qu’il Exchange Online les courriers électroniques générés dans Microsoft 365 et Teams arrivent correctement dans Gmail. Les valeurs par défaut de sécurité doivent être désactivées pour accomplir cette connexion, ce qui rend essentiel l’utilisation d’un mot de passe fort unique. Un domaine personnalisé n’est pas nécessaire pour ce scénario, mais il peut être configuré dans Microsoft 365 pour une utilisation dans Gmail si vous voulez en utiliser un.

:::image type="content" source="media/essentials-gmail.png" alt-text="Image de citez le flux de courrier électronique entre Teams Essentials et Gmail":::

**Assurez-vous de configurer un compte Gmail.**

Si vous avez déjà un compte, vous pouvez passer à l’étape suivante. Si ce n’est [pas le cas, visitez Créer un compte Google](https://accounts.google.com/SignUp?hl=en) pour configurer un nouveau compte Gmail.

**2. Configurer votre client Microsoft 365 client**

*Configurer les utilisateurs Teams AAD utilisateurs*

1. Suivez les instructions de [AtAdd users et attribuez des licences pour](/microsoft-365/admin/add-users/add-users?view=o365-worldwide&preserve-view=true) ajouter plusieurs utilisateurs

*Configurer la protection des identités*

1. Désactivez les valeurs de sécurité par défaut si actives.

2. Configurer l’authentification multifacteur pour les utilisateurs

3. Si vous utilisez l’accès conditionnel, veillez à faire exception pour l’accès POP à la boîte aux lettres

*Ajouter un domaine Administration Microsoft 365 Centre d’activités (facultatif)*

1. Sous Navigation, sélectionnez Paramètres > domaine, puis sélectionnez Ajouter un domaine

2. Entrez votre nom de domaine dans le champ approprié

3. Suivez les instructions à l’écran pour vérifier votre domaine auprès de l’enregistrement TXT

4. À l’invite, autorisez Microsoft à configurer le DNS

5. Complétez les instructions de vérification de l’itinéraire de l’enregistrement MX pour Microsoft 365

6. Configurer l’enregistrement TXT SPF de façon à ce qu’il Microsoft 365

7. Complétez les instructions de configuration des enregistrements TXT DKIM pour Microsoft 365

8. Vérifiez que DKIM est activé en vous dé connectant et en vous connectant à nouveau au Centre d’administration

**3. Configurer Gmail**

1. Configurer Gmail pour retirer du courrier Exchange Online son système

2. Configurer le Teams calendrier

3. Activer Gmail pour utiliser le domaine d’entreprise (facultatif)
