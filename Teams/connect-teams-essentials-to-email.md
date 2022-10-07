---
title: Connecter Microsoft Teams Essentials (identité AAD) à un système de messagerie existant avec un calendrier
ms.author: mikeplum
author: MikePlumleyMSFT
ms.reviewer: jimmyw
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: Découvrez comment connecter Microsoft Teams Essentials (identité AAD) à un système de messagerie existant avec un calendrier comme Google Workspace
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: acdd613044e5e7f0ac7db857ca734f276522c919
ms.sourcegitcommit: 6e85f3f70f8488ab827ac352c0f324b6dfd4b856
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2022
ms.locfileid: "68377592"
---
# <a name="connect-microsoft-teams-essentials-aad-identity-to-an-existing-email-system-with-calendar"></a>Connecter Microsoft Teams Essentials (identité AAD) à un système de messagerie existant avec un calendrier

Ce guide fournit des étapes de configuration pour connecter Microsoft Teams Essentials (identité AAD) à un système de messagerie existant avec un calendrier.

Microsoft Teams Essentials (identité AAD) réunit le meilleur de Teams avec des réunions, des conversations, des appels et une collaboration. Teams Essentials (AAD Identity) peut se connecter à votre système de messagerie existant pour fournir une expérience intégrée, comme la présence de toutes les notifications Teams dans une boîte de réception de courrier existante, tous les événements de calendrier dans Teams et la possibilité de se connecter à Teams avec votre adresse e-mail existante.

Une fois connecté, vous pouvez voir les réponses aux réunions planifiées et aux invitations à collaborer dans votre boîte aux lettres et Microsoft Teams. Vous pouvez également afficher et interagir avec les réunions entrantes à partir de votre calendrier à l’aide de Teams et de logiciels de réunion tiers tels que Google Workspace.

## <a name="prerequisites"></a>Conditions préalables

Les étapes de configuration décrites dans cet article impliquent le processus de transfert automatique d’éléments à partir de Exchange Online. Par défaut, le transfert automatique est désactivé par la stratégie de trafic sortant anti-courrier indésirable. Cette stratégie doit être activée pour connecter Teams Essentials à une boîte aux lettres et un système de calendrier existants.

Pour activer le transfert automatique :

1. Accédez au portail Microsoft 365 Defender à l’adresse<https://security.microsoft.com/>
2. Dans le menu de navigation de gauche, accédez à Email & stratégies de **collaboration** > **& règles** > **contre** >  le **courrier indésirable** dans la section Stratégies
3. Dans la page **Stratégies anti-courrier indésirable** , sélectionnez **Stratégie de trafic sortant anti-courrier indésirable (par défaut)** dans la liste
4. Dans le menu volant des détails de stratégie qui s’affiche, sélectionnez **Modifier les paramètres de protection** pour modifier la règle de transfert automatique.
5. Sous **règles de transfert**, remplacez la condition de transfert automatique **par Activé : le transfert est activé** et enregistrez vos modifications.

:::image type="content" source="media/essentials-antispam.png" alt-text="Image montrant le menu volant de stratégie de trafic sortant anti-courrier indésirable du portail Microsoft Defender avec Activé, le transfert est activé sous les règles de transfert." :::

Pour en savoir plus sur la configuration des stratégies de courrier indésirable sortant, consultez [Configurer le filtrage du courrier indésirable sortant - Office 365 | Microsoft Docs](/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide&preserve-view=true).

## <a name="connect-teams-essentials-to-exchange-online-with-exchange-on-premises"></a>Connecter Teams Essentials à Exchange Online avec Exchange en local

Vous pouvez profiter de tout ce que Teams Essentials (AAD) a à offrir à l’aide d’une approche hybride pour configurer la connexion entre Microsoft Teams et Exchange Online avec Exchange en local.

Pour que l’accès au calendrier fonctionne pour vos boîtes aux lettres locales, suivez les instructions fournies lors de la[configuration de l’accès au calendrier Teams pour les boîtes aux lettres Exchange locales - Microsoft Tech Community](https://techcommunity.microsoft.com/t5/exchange-team-blog/configuring-teams-calendar-access-for-exchange-on-premises/ba-p/1484009)

Pour déployer Salles Microsoft Teams dans un environnement hybride avec Exchange en local, [visitez Deploy Salles Microsoft Teams with Exchange on-premises - Microsoft Teams | Microsoft Docs](rooms/with-exchange-on-premises.md)

## <a name="connect-teams-essentials-to-third-party-email-systems-with-calendar"></a>Connecter Teams Essentials à des systèmes de messagerie tiers avec un calendrier

Si vous n’envisagez pas de basculer la boîte aux lettres de votre organisation vers Microsoft 365, vous pouvez connecter Teams Essentials à un système de messagerie et de calendrier tiers existant. Cette connexion vous permet de recevoir des notifications Teams dans votre système de messagerie existant lors de l’affichage des invitations aux réunions et des événements de calendrier existants dans Microsoft Teams.

### <a name="connect-teams-essentials-to-third-party-email-using-vanity-domain-google-workspace-example"></a>Connecter Teams Essentials à des e-mails tiers à l’aide d’un domaine personnel (exemple d’espace de travail Google)

La section suivante vous montre comment connecter Microsoft Teams à un système de messagerie existant avec un calendrier, comme Google Workspace. Vous allez effectuer cette connexion en laissant le système de messagerie actuel intact, en transférant tous les e-mails à Exchange Online, en filtrant tout ce qui est sauf les e-mails du type de calendrier. Ce faisant, les e-mails de calendrier apparaissent automatiquement dans le calendrier Teams accepté en tant qu’e-mails de type provisoire et non calendrier sont supprimés.

Tous les e-mails générés dans Microsoft 365 sont transférés vers Google Workspace afin que les utilisateurs reçoivent des rappels et des notifications Teams. Les identités utilisateur, comme l’e-mail principal de l’utilisateur, peuvent être dupliquées. L’authentification unique est également possible, mais pas obligatoire. Les utilisateurs doivent être en mesure de rejoindre des réunions Teams à partir du calendrier tiers ou du calendrier Teams. D’autres fonctionnalités teams fonctionneront comme prévu.

:::image type="content" source="media/essentials-googleworkspace.png" alt-text="Image représentant un diagramme du flux de messagerie entre EXO et Gmail":::

Ces exemples s’appuient sur l’applet de commande [Connect-ExchangeOnline](/powershell/module/exchange/connect-exchangeonline) PowerShell qui fait partie du [module PowerShell V2 Exchange Online](/powershell/exchange/exchange-online-powershell-v2?preserve-view=true&view=exchange-ps). Si vous recevez une erreur lors de l’exécution de Connect-ExchangeOnline, vérifiez que vous avez suivi les instructions recommandées pour l’installation du module à [l’aide de l’installation du module EXO V2](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-EXO-v2-module). Lorsque Connect-ExchangeOnline demande des informations d’identification, veillez à utiliser un compte d’administrateur client.

#### <a name="step-one-set-up-a-new-microsoft-365-tenant-domain"></a>Étape 1 : Configurer un nouveau domaine client Microsoft 365

1. Accédez au centre d’administration à l’adresse <https://admin.microsoft.com>.

2. Accédez à **Configurer** > **des domaines**  et **sélectionnez Ajouter un domaine** pour ajouter votre domaine existant. Si vous n’ajoutez pas de domaine, les membres de votre organisation utiliseront le domaine onmicrosoft.com pour leurs adresses e-mail jusqu’à ce que vous le fassiez. Veillez à ajouter votre domaine avant d’ajouter des utilisateurs, afin de ne pas avoir à les configurer deux fois.

3. Vérifiez le domaine avec un enregistrement TXT en suivant les étapes décrites dans [Vérifier avec un enregistrement TXT](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider?view=o365-worldwide&preserve-view=true).

4. Lorsque vous y êtes invité, **sélectionnez Ne pas autoriser Microsoft 365 à configurer DNS**.

5. Lorsque vous y êtes invité, laissez les enregistrements MX existants en place sans les modifier.

6. Mettez à jour l’enregistrement TXT SPF existant pour inclure Microsoft 365.

7. Configurez DomainKeys Identified Mail (DKIM) pour Microsoft 365 en suivant ces étapes pour configurer manuellement [DKIM](/microsoft-365/security/office-365-security/use-dkim-to-validate-outbound-email?view=o365-worldwide&preserve-view=true).

8. Se connecter à l’Centre d'administration Microsoft 365 pour <https://admin.microsoft.com/AdminPortal/> activer DKIM

9. Dans le panneau de navigation à gauche, sélectionnez **Domaines** **d’installation** > 

10. À l’aide de la case à cocher, sélectionnez votre domaine non Microsoft existant (par exemple, TomislavK@thephone-company.com) dans les listes de domaines actuelles.

11. Sélectionnez le bouton avec **trois points verticaux** pour ouvrir un menu.

12. Dans le menu, **sélectionnez Définir par défaut**

13. **Confirmez la valeur par défaut** dans la fenêtre qui semble définir votre domaine existant comme valeur par défaut.
    :::image type="content" source="media/essentials-internalrelay2.png" alt-text="Image de la boîte de dialogue de confirmation pour définir le domaine comme domaine par défaut":::

    Pour plus d’informations sur l’ajout d’un domaine à Microsoft 365, suivez les étapes décrites dans [Ajouter un domaine à Microsoft 365](https://support.office.com/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US).

#### <a name="step-two-add-users-and-assign-teams-essentials-licenses"></a>Étape 2 : Ajouter des utilisateurs et attribuer des licences Teams Essentials

1. Accédez au centre <https://admin.microsoft.com> d’administration pour ajouter un utilisateur individuel

2. Accédez à **Utilisateurs** > **actifs**, puis **sélectionnez Ajouter un utilisateur**

3. Dans le volet **Configurer les informations de base** , renseignez les informations utilisateur de base, puis sélectionnez **Suivant**.
    - **Nom:** Renseignez le prénom et le nom, le nom d’affichage et le nom d’utilisateur.
    - **Domaine:** Choisissez le domaine du compte de l’utilisateur. Par exemple, si le nom d’utilisateur de l’utilisateur est Jakob et que le domaine est contoso.com, il se connecte à l’aide de jakob@contoso.com.
    - **Paramètres de mot de passe :** Choisissez d’utiliser le mot de passe généré automatiquement ou de créer votre propre mot de passe fort pour l’utilisateur.  Déterminez si vous souhaitez envoyer le mot de passe dans un e-mail lorsque l’utilisateur est ajouté.

4. Dans le volet **Attribuer des licences de produit** , sélectionnez l’emplacement et la licence appropriée pour l’utilisateur. Si vous n’avez pas de licences disponibles, vous pouvez toujours ajouter un utilisateur et acheter d’autres licences. Sélectionnez Suivant.

5. Dans le volet **Paramètres facultatifs** , développez **Rôles** si vous souhaitez que cet utilisateur soit administrateur. Développez **les informations de profil** pour ajouter des informations supplémentaires sur l’utilisateur.

6. Sélectionnez **Suivant**, passez en revue les paramètres de votre nouvel utilisateur, apportez d’autres modifications si nécessaire, puis sélectionnez **Terminer l’ajout**, puis fermez.

Pour ajouter plusieurs utilisateurs en même temps, suivez les étapes [recommandées dans Ajouter des utilisateurs et attribuer des licences - Administrateur Microsoft 365 | Microsoft Docs](/microsoft-365/admin/add-users/add-users?view=o365-worldwide&preserve-view=true)

#### <a name="step-three-configure-google-workspace"></a>Étape 3 : Configurer l’espace de travail Google

***Configurez la remise par e-mail double à Microsoft 365 et supprimez les pièces jointes :***

1. Suivez les étapes de Google pour configurer la double livraison : <https://support.google.com/a/answer/9228551?hl=en>

2. Ajouter un itinéraire pour Office 365

    - Accédez à la console Google Administration à l’adresse <https://admin.google.com>)
    - Accédez à Apps > Google Workspace > Gmail > Hosts.
    - Entrez un nom de route. (Par exemple, Microsoft 365)
    - Choisissez « Hôte unique » et entrez l’enregistrement MX spécifié pour le domaine dans Microsoft 365 (par exemple : ContosoLandscaping2-m365master-com.mail.protection.outlook.com)

    **Méthode hôte intelligente pour résoudre le code de réponse ATTR35 lorsque le courrier est envoyé à Exchange en local/Exchange Online :**
    - Choisissez « Hôte unique » et entrez l’enregistrement MX pour le domaine initial du locataire en tant qu’hôte intelligent. Le domaine initial est au format GUID.onmicrosoft.com. Un GUID est une valeur unique fournie à chaque organisation dans le cadre de son inscription au service. Un GUID est un entier 128 bits (16 octets) qui peut être utilisé sur tous les ordinateurs et réseaux partout où un identificateur unique est requis.
    - Vous pouvez utiliser la ligne de commande : nslookup -type MX GUID.onmicrosoft.com pour résoudre l’enregistrement MX (par exemple : contosolandscaping2.mail.protection.outlook.com)
    - Choisir **le port :25**
    - Continuer avec les options recommandées

3. Configurer l’itinéraire vers Office 365

    - Ouvrez la **console Google Administration** à l’adresse<https://admin.google.com>

    - Accéder au **routage** **Gmail** >  de **l’espace** >  de travail Google **Apps** > 

    - Sous l’onglet **Routage** , sélectionnez **Configurer**

    - Entrez **le nom** de la règle. (Par exemple, Gmail vers Office 365)

    - Pour **que les messages électroniques affectent**, sélectionnez à la fois **réception entrante** et  **réception interne**

    - Sous **Pour les types de messages ci-dessus**, sélectionnez **Modifier le message**

    - Sous **Également remettre à**, **sélectionnez Ajouter d’autres destinataires** , puis **sélectionnez Ajouter pour ajouter l’itinéraire de messagerie secondaire.**

    - Sous **Destinataires**, sélectionnez la flèche vers le bas « » et sélectionnez **Avancé.**

    - Sélectionnez **Modifier l’itinéraire.**

    - Dans la liste, sélectionnez l’itinéraire de messagerie secondaire que vous avez créé précédemment

    - Sous **Pièces jointes**, **sélectionnez Supprimer les pièces jointes du message**

    - Faites défiler vers le bas et **sélectionnez Enregistrer**.

***Ajoutez votre sous-domaine dans l’espace de travail Google pour recevoir des e-mails de Microsoft 365.***

  Ensuite, vous allez créer des règles de transfert sur les boîtes aux lettres Microsoft 365 vers votre sous-domaine. Choisissez un sous-domaine à utiliser dans Google Workspace pour recevoir des e-mails de Microsoft 365 (par exemple, g.contosolandscaping2.m365master.com)

1. Démarrer sur la **console Google Administration** (à admin.google.com)

2. Accéder à **Account** > **Domains** > **Manage Domains**

3. Sélectionnez **Ajouter un domaine**

4. Entrez le nom de domaine que vous avez sélectionné

5. Sélectionner **un domaine d’alias d’utilisateur**

6. Sélectionnez **Ajouter un domaine & démarrer la vérification**

7. Attendre la fin de la vérification et actualiser la page

8. Sélectionnez **Activer Gmail**

9. Choisissez **Ignorer la configuration de l’enregistrement MX** , puis sélectionnez **SUIVANT**

10. Dans la boîte de **dialogue Router le courrier vers un autre serveur**, notez le serveur vers lequel acheminer le courrier (par exemple, aspmx.l.google.com) et sélectionnez **J’utilise un autre serveur de messagerie**.

***Autoriser les e-mails de Microsoft 365 à contourner le filtre de courrier indésirable***

1. Recherchez un en-tête approprié à partir du locataire Microsoft 365 en envoyant un e-mail à un utilisateur sur l’espace de travail Google.

2. Ouvrez le message et **sélectionnez Afficher l’original**

3. Choisissez un en-tête d’e-mail qui identifie de manière unique le courrier provenant de votre locataire Microsoft 365. (Par exemple, X-MS-Exchange-CrossTenant-id : 92f60fc7-eab3-403b-9d7d-9d683bf0a4b5)

4. Accédez à la **console Google Administration** à l’adresse<https://admin.google.com>

5. Accédez à **Applications** > **Google Workspace** > **Gmail** > **Compliance**

6. Accédez à **Conformité du contenu** et **sélectionnez Configurer**

7. Donnez un nom au paramètre. Par exemple, allowlist Microsoft 365 email.

8. Sous **messages électroniques pour affecter la** vérification entrante

9. Sous **Ajouter des expressions qui décrivent le contenu que vous souhaitez rechercher dans chaque message** , sélectionnez **si l’une des expressions suivantes correspond au message**

10. Sous **Expressions**, **sélectionnez Ajouter** xi. Sous **Ajouter un paramètre**, choisissez **Correspondance de contenu avancé**

11. Sous **Emplacement** , choisissez **En-têtes complets**

12. Sous **Type de correspondance** , choisissez **Texte intégral**

13. Sous le contenu, entrez l’en-tête d’e-mail qui identifie de manière unique les e-mails provenant de votre locataire Microsoft 365 (par exemple, X-MS-Exchange-CrossTenant-id : 92f60fc7-eab3-403b-9d7d-9d683bf0a4b5)

14. Sélectionnez **Enregistrer**

15. Dans **l’option Si les expressions ci-dessus correspondent, effectuez le champ suivant** > **Modifier le message** et vérifiez ignorer le **filtre anti-courrier indésirable pour ce message** sous **Courrier indésirable**.

16. Sélectionnez **Enregistrer**

#### <a name="step-four-configure-microsoft-365-settings-for-the-integration"></a>Étape 4 : Configurer les paramètres Microsoft 365 pour l’intégration

*Configurez le connecteur pour acheminer le courrier de Microsoft 365 vers Gmail :*

1. Accédez au **Centre de Administration Microsoft** à l’adresse<https://admin.microsoft.com/AdminPortal>

2. Sélectionnez **Afficher tout** dans le menu de navigation de gauche.

3. Sous **Administration centres**, sélectionnez **Exchange** pour ouvrir le centre d’administration Exchange dans un nouvel onglet

4. Dans le menu de navigation de gauche du **centre d’administration Exchange**, sélectionnez **Connecteurs** de **flux** >  de courrier, ouvrez le menu de dépassement (...) et sélectionnez Ajouter un connecteur

5. Sous **Connexion à partir de** la nouvelle fenêtre du connecteur, sélectionnez **Office 365**

6. Sous **Connexion pour** sélectionner le serveur de messagerie de votre organisation, puis sélectionnez **Suivant**

7. Entrez un **nom** pour le nouveau connecteur (par exemple, Vers Gmail) et continuez **Suivant**

8. Dans la section **Utilisation du connecteur** , sélectionnez **Uniquement lorsque j’ai configuré une règle de transport qui redirige les messages vers ce connecteur** , puis **sélectionnez Suivant**.

9. Dans la section Routage, entrez l’hôte de messagerie intelligent approprié (par exemple, aspmx.l.google.com), sélectionnez **+**, puis **continuez Suivant**.

10. Dans la section **Restrictions de sécurité** , acceptez les paramètres par défaut en sélectionnant **Suivant**

11. Dans la **section Validation email**, entrez une adresse e-mail valide pour le système Gmail (par exemple, johannal@g.contosolandscaping2.m365master.com), sélectionnez le **signe plus (+)**, puis **sélectionnez Valider**

12. Attendez la fin de la validation et, si la validation réussit, appuyez sur Suivant

13. Sous **Passer en revue le connecteur**, vérifiez que la configuration est correcte et appuyez sur Créer un connecteur

14. Lorsque vous voyez la notification créée par le connecteur, appuyez sur **Terminé**

*Transférer le courrier des boîtes aux lettres Microsoft 365 vers Gmail :*

1. Utilisez le **centre Administration Microsoft 365** pour mettre à jour chaque boîte aux lettres ou vous pouvez utiliser un script **PowerShell**, comme suit :

    ```powershell
    $forwardingDomain = "g.contosolandscaping2.m365master.com"
    Connect-ExchangeOnline
    $Mailboxes = Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"}
    Foreach ($mbx in $mailboxes) {

    Set-Mailbox $mbx.Identity -DeliverToMailboxAndForward $true -ForwardingSMTPAddress $($mbx.Alias,$forwardingDomain -join "@")
    }
    ```

    **Résolution des problèmes liés à Connect-ExchangeOnline :**

    Rencontrez-vous une erreur lors de l’exécution de Connect-ExchangeOnline ? Cela peut être le résultat de la règle de transfert automatique de courrier électronique de votre organisation. Par défaut, le transfert automatique est désactivé. Pour connecter Teams Essentials à Google Workspace, la règle doit être activée.

    Entrez le script suivant :

   ```powershell
    Set-ExecutionPolicy Unrestricted
     ```

    Ensuite, exécutez les commandes suivantes :

    ```powershell
    Enable-OrganizationCustomization
    Get-HostOutboundSpamFilterPolicy | set-HostedOutboundSpamFilterPolicy -AutoForwardingMode On
    ```

*Configurez Exchange Online règle de transport direct vers le calendrier :*

1. La configuration de ce paramètre accepte automatiquement les invitations de calendrier afin qu’elles s’affichent dans le calendrier Teams sans obliger les utilisateurs à interagir avec l’invitation dans Outlook Web App.

2. Le script suivant peut être utilisé pour créer les règles de transport :

    ```powershell
    Connect-ExchangeOnline
    New-TransportRule -Name "Direct to Calendar" -MessageTypeMatches Calendaring -SetHeaderName "X-MS-Exchange-Organization-CalendarBooking-Response" -SetHeaderValue Tentative
    New-TransportRule -Name "Direct to Calendar triage action" -MessageTypeMatches Calendaring -SetHeaderName "X-MS-Exchange-Organization-CalendarBooking-TriageAction" -SetHeaderValue MoveToDeletedItems

    ```

*Désactivez Outlook sur le web pour les boîtes aux lettres :*

1. Suivez les instructions fournies dans [Activer ou désactiver Outlook sur le web d’une boîte aux lettres dans Exchange Online](/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app) pour désactiver Outlook sur le web pour les boîtes aux lettres.

2. Vous pouvez désactiver Outlook sur le web à l’aide du **Centre de Administration Exchange** ou **de PowerShell**. Vous pouvez utiliser l’exemple PowerShell suivant pour désactiver Outlook sur le web pour toutes les boîtes aux lettres :

    ```powershell
    Connect-ExchangeOnline
    $Mailboxes = Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"}
    Foreach ($mbx in $mailboxes) {
    Set-CASMailbox $mbx.Identity -OWAEnabled $false
    }
    ```

#### <a name="step-five-configure-exchange-online-domain-for-internal-relay"></a>Étape 5 : Configurer Exchange Online domaine pour le relais interne

Cette étape garantit que l’e-mail est envoyé au système tiers pour une résolution finale.

1. Accédez au **Centre de Administration Microsoft** à l’adresse<https://admin.microsoft.com/AdminPortal>

2. Dans la navigation de gauche, sélectionnez **Afficher tout**

3. Sous **Administration Centres**, sélectionnez **Exchange** pour ouvrir le Centre d’administration Exchange dans un nouvel onglet

4. Dans le **Centre d’administration Exchange**, sélectionnez **Flux de courrier** dans le menu de navigation de gauche, puis sélectionnez **Domaines acceptés**

5. Appuyez sur le nom de domaine configuré dans le système tiers (par exemple, contosoLandscaping2.m365master.com)

    :::image type="content" source="media/essentials-internalrelay1.png" alt-text="Image montrant les paramètres du Centre d’administration Exchange pour le flux de messagerie. ":::

6. Sélectionnez **Relais interne**, puis cliquez sur **Enregistrer**

    :::image type="content" source="media/essentials-internalrelay2.png" alt-text="Image montrant l’action d’enregistrement du paramètre de relais interne.":::

#### <a name="step-six-create-a-rule-to-delete-all-inbound-mail-to-exchange-online-except-for-calendaring"></a>Étape 6 : Créer une règle pour supprimer tous les messages entrants vers Exchange Online à l’exception du calendrier

1. Vous pouvez configurer cette règle dans exchange **Administration Center** ou **PowerShell**. Vous pouvez utiliser l’exemple **PowerShell** suivant pour créer la règle :

    ```powershell
    Connect-ExchangeOnline
    New-TransportRule -Name "Delete all except Calendaring" -ExceptIfMessageTypeMatches Calendaring -FromScope NotInOrganization -DeleteMessage:$true
    ```

### <a name="connect-teams-essentials-to-third-party-email-not-using-vanity-domain-gmail-example"></a>Connecter Teams Essentials à des e-mails tiers qui n’utilisent pas de domaine personnel (exemple Gmail)

Vous pouvez planifier et participer à une réunion Teams directement à partir de Google Workspace en connectant un compte Gmail consommateur à Teams Essentials, en vous appuyant principalement sur [l’extension Teams G Suite](https://support.microsoft.com/office/install-the-teams-meeting-add-on-for-google-workspace-bba2dfbe-0b2b-4ee7-be10-261ad80ddb60). Cela vous donne la possibilité de planifier la vidéo et l’audioconférence avec partage d’écran, conversation de réunion, tableaux blancs numériques, etc.

Vous allez configurer Gmail pour extraire les e-mails de Exchange Online pour vous assurer que les messages générés dans Microsoft 365 et Teams arrivent correctement dans Gmail. Les paramètres de sécurité par défaut peuvent avoir besoin d’être désactivés pour effectuer cette connexion, ce qui rend l’utilisation d’un mot de passe unique fort essentiel. Un domaine personnalisé n’est pas nécessaire pour ce scénario, mais il peut être configuré dans Microsoft 365 pour une utilisation dans Gmail si vous souhaitez en utiliser un.

:::image type="content" source="media/essentials-gmail.png" alt-text="Image dépençant le flux de courrier entre Teams Essentials et Gmail":::

#### <a name="1-ensure-that-you-have-a-gmail-account-set-up"></a>1. Vérifiez que vous disposez d’un compte Gmail configuré

Si vous disposez déjà d’un compte existant, vous pouvez passer à l’étape suivante. Si ce n’est pas le cas, [visitez Créer un compte Google](https://accounts.google.com/SignUp?hl=en) pour configurer un nouveau compte Gmail.

#### <a name="2-set-up-your-microsoft-365-tenant"></a>2. Configurer votre locataire Microsoft 365

*Configurer les utilisateurs Teams AAD :*

1. Suivez les instructions sur[Ajouter des utilisateurs et attribuez des licences](/microsoft-365/admin/add-users/add-users?view=o365-worldwide&preserve-view=true) pour ajouter plusieurs utilisateurs

*Configurer la protection des identités :*

1. Désactivez les paramètres de sécurité par défaut s’ils sont actifs.

2. Configurer l’authentification multifacteur pour les utilisateurs

3. Si vous utilisez l’accès conditionnel, veillez à faire une exception pour l’accès POP à la boîte aux lettres

*Ajouter un domaine à Administration Microsoft 365 Center (facultatif) :*

1. Sous navigation, sélectionnez Paramètres > Domaine, puis Sélectionnez Ajouter un domaine

2. Entrez votre nom de domaine dans le champ approprié

3. Suivez les instructions à l’écran pour vérifier votre domaine avec l’enregistrement TXT

4. Lorsque vous y êtes invité, autorisez Microsoft à configurer DNS

5. Suivez les instructions pour vérifier la route d’enregistrement MX vers Microsoft 365

6. Configurer l’enregistrement TXT SPF pour inclure Microsoft 365

7. Suivez les instructions de configuration des enregistrements TXT DKIM pour Microsoft 365

8. Vérifier que DKIM est activé en déconnectant et en se connectant au centre de Administration

#### <a name="3-configure-gmail"></a>3. Configurer Gmail

1. Configurer Gmail pour extraire Exchange Online courrier dans son système

2. Configurer le complément Calendrier Teams

3. Activer Gmail pour utiliser le domaine d’entreprise (facultatif)
