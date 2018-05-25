---
title: Conception et création de flux de travail Response Group dans Skype Entreprise 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: dcb9effb-5d12-4dee-80fc-ab9654222d5a
description: Concevoir et créer des flux de travail Response Group dans Skype pour Business Server Enterprise Voice. Les flux de travail de groupe de recherche et les flux de travail interactifs sont tous les deux couverts.
ms.openlocfilehash: 21c4b5beb8b4653bc31481d956f235a2c4fe722e
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/24/2018
---
# <a name="designing-and-creating-response-group-workflows-in-skype-for-business-2015"></a>Conception et création de flux de travail Response Group dans Skype Entreprise 2015
 
Concevoir et créer des flux de travail Response Group dans Skype pour Business Server Enterprise Voice. Les flux de travail de groupe de recherche et les flux de travail interactifs sont tous les deux couverts.
  
Un flux de travail définit le comportement d’un appel, du déclenchement de la sonnerie du téléphone jusqu’au moment où une personne répond à l’appel. Le flux de travail spécifie la file d’attente à utiliser pour la conservation de l’appel et spécifie la méthode de routage à utiliser pour le flux de travail de groupe recherche ou les questions et réponses à utiliser pour le flux de travail de groupe réponse interactif. 
  
Un flux de travail définit également des paramètres, comme un message de bienvenue, l’attente musicale, les heures de bureau et les vacances.
  
> [!NOTE]
> Vous devez créer des groupes d’agents et des files d’attente avant de créer un flux de travail qui les utilise. 
  
## <a name="creating-or-modifying-a-hunt-group-workflow"></a>Création ou modification d’un flux de travail de groupe de recherche

### <a name="to-use-response-group-configuration-tool-to-create-or-modify-a-hunt-group-workflow"></a>Pour utiliser l’outil de Configuration pour Response Group pour créer ou modifier un flux de travail de groupe de recherche

1. Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre d’un des rôles d’administrateur prédéfinis qui prennent en charge Response Group.
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.  
    
3. Dans la barre de navigation de gauche, cliquez sur **Services Response Group**, puis sur **Flux de travail**.
    
4. Dans la page **Flux de travail**, cliquez sur **Créer ou modifier un flux de travail**.
    
5. Dans le champ **Sélectionner un Service** de recherche, tapez entièrement ou partiellement le nom du service **ApplicationServer** qui héberge le flux de travail que vous souhaitez créer ou modifier. Dans la liste de services qui s’affiche, cliquez sur le service de votre choix, puis sur **OK**.
    
    > [!NOTE]
    > L’outil de Configuration Response Group s’ouvre. Vous pouvez également ouvrir l’outil de Configuration Response Group directement à partir d’un navigateur web en tapant l’URL suivante : https:// _ \<webPoolFqdn\>_/RgsConfig. 
  
6. Effectuez l’une des actions suivantes :
    
   - Sous **Créer un flux de travail**, en regard de **Groupe de recherche, cliquez sur Créer**.
    
   - Sous **Gérer un flux de travail existant**, recherchez le flux de travail à modifier, puis sous **Action**, cliquez sur **Modifier**.
    
7. Si vous êtes prêt et que les utilisateurs peuvent commencer à appeler le flux de travail, activez la case à cocher **Activer le flux de travail**.
    
    > [!NOTE]
    >  Si vous créez un flux de travail géré, vous devez sélectionner **Activer le flux de travail**. Une fois que vous avez enregistré le flux de travail géré actif, vous pouvez le modifier et le désactiver. 
  
8. Pour autoriser les utilisateurs fédérés à appeler le groupe, activez la case à cocher **Activer pour la fédération**. Vous devez également disposer d’une stratégie d’accès externe qui s’applique à l’application Response Group configurée pour la fédération.
    
    > [!NOTE]
    > La stratégie d’accès externe globale s’applique à l’application Response Group. Vous pouvez configurer la stratégie globale pour la fédération de groupe de réponse à l’aide de Skype pour le panneau de configuration serveur Business ou à l’aide de l’applet de commande **Set-CsExternalAccessPolicy** pour définir le paramètre EnableOutsideAccess sur True. Gardez à l’esprit que les paramètres de stratégie globale s’appliquent à tous les utilisateurs sauf s’ils sont affectés à un site ou une stratégie d’utilisateur. Par conséquent, avant de modifier ce paramètre pour les groupes Response Group, assurez-vous que le paramètre de fédération satisfait les exigences de votre organisation. Pour plus d’informations sur comment appliquent des stratégies pour les utilisateurs, voir [Gestion d’une stratégie d’accès externe pour votre organisation](http://technet.microsoft.com/library/5571811e-34c8-443a-b94c-1ab5d4275581.aspx). Pour plus d’informations sur le paramètre de fédération, voir [Set-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/set-csexternalaccesspolicy?view=skype-ps). 
  
    > [!NOTE]
    > Les utilisateurs qui sont hébergées dans Skype pour Business Online ne peuvent pas passer des appels à des groupes de réponses qui sont hébergées dans un déploiement sur site. Cela est vrai dans les deux déploiements hybrides et dans les cas où un déploiement sur site est fédéré avec une Skype pour le déploiement d’entreprise en ligne. 
  
9. Pour masquer l’identité des agents pendant les appels, activez la case à cocher **Activer l’anonymat de l’agent**.
    
    > [!NOTE]
    > Les appels anonymes ne peuvent pas commencer par la messagerie instantanée ou la vidéo, mais l’agent ou l’appelant peut ajouter la messagerie instantanée et la vidéo une fois que l’appel a commencé. Un agent anonyme peut également mettre des appels en attente, transférer des appels (transferts invisibles et consultatifs), mais aussi parquer et récupérer des appels. Les appels anonymes ne prennent pas en charge la conférence, le partage d’application, le partage du Bureau, le transfert de fichiers, le tableau blanc, la collaboration de données et l’enregistrement d’appel. Les agents utilisant le plugin Lync VDI peuvent recevoir des appels entrants anonymes, mais ils ne peuvent pas effectuer d’appels sortants anonymes. 
  
10. Sous **Entrez l’adresse du groupe qui recevra les appels**, cliquez sur l’adresse URI SIP (Session Initiation Protocol) principale du groupe qui doit prendre les appels vers le flux de travail.
    
    > [!NOTE]
    > L’URI principal pour un flux de travail définit les modalités d’identification et de référencement du flux de travail. L’URI SIP que vous entrez est créée en tant qu’objet contact dans les Services de domaine Active Directory. Pour créer l’URI, l’objet doit être unique dans Active Directory. 
  
11. Dans la zone **nom complet**, tapez le nom que vous souhaitez afficher pour le flux de travail (par exemple, ventes Response Group).
    
    > [!NOTE]
    > N’incluez pas les caractères « < » ni « > » dans le nom d’affichage. N’utilisez pas les noms d’affichage ci-dessous, car ils sont réservés : **RGS Presence Watcher** ou **Service d’annonce**. 
  
12. Sous **Numéro de téléphone**, tapez l’URI de ligne pour le groupe Response Group (par exemple, +14255550165).
    
13. Dans **Numéro affiché**, tapez le numéro tel qu’il doit s’afficher pour le groupe Response Group (par exemple, +1 (425) 555-0165).
    
14. (Facultatif) Dans la zone **Description**, tapez une description pour le flux de travail que vous souhaitez qu’il apparaisse sur la carte de visite dans Skype pour les entreprises.
    
15. Dans **Type de flux de travail**, sélectionnez **Géré** si ce flux de travail sera géré par un responsable de groupes Response Group. Procédez comme suit pour affecter des responsables de groupe de réponse pour le flux de travail :
    
    a. Tapez l’URI SIP (Session Initiation Protocol) d’un responsable pour ce flux de travail, puis cliquez sur **Ajouter**.
    
    b. Tapez l’URI SIP (Session Initiation Protocol) d’autres responsables à ajouter au flux de travail, puis cliquez sur **Ajouter**.
    
    > [!IMPORTANT]
    > Tous les utilisateurs désignés comme responsables d’un groupe Response Group doivent posséder le rôle CsResponseGroupManager. Si les utilisateurs n’ont pas ce rôle, ils ne peuvent pas gérer les groupes Response Group. 
  
16. Dans **Étape 2 Sélection d’une langue**, cliquez sur la langue à utiliser pour la reconnaissance vocale et la conversion de texte par synthèse vocale.
    
17. Si vous souhaitez configurer un message de bienvenue, dans **Étape 3 Configuration d’un message de bienvenue**, activez la case à cocher **Lisez un message de bienvenue**, puis effectuez l’une des opérations suivantes :
    
   - Pour entrer le message de bienvenue sous forme de texte converti en message vocal pour les appelants, cliquez sur **Utiliser la synthèse vocale**, puis tapez le message de bienvenue dans la zone de texte.
    
    > [!NOTE]
    > N’incluez pas de balises HTML dans le texte que vous entrez. Si vous incluez des balises HTML, vous recevrez un message d’erreur. 
  
   - Pour utiliser un enregistrement de fichier son (.wav) ou audio Windows Media (.wma) pour le message de bienvenue, cliquez sur **Sélectionner un enregistrement**. Si vous souhaitez télécharger un nouveau fichier audio, cliquez sur le lien **un enregistrement**. Dans la nouvelle fenêtre de navigateur, cliquez sur **Parcourir**, sélectionnez le fichier audio à utiliser, puis cliquez sur **Ouvrir**. Cliquez sur **Télécharger** pour charger le fichier audio.
    
    > [!NOTE]
    > Tous les fichiers audio fournis aux utilisateurs doivent remplir certains critères. Pour plus d’informations sur les formats de fichiers pris en charge, voir [Configuration technique requise pour les groupes de réponses](http://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx). 
  
18. Dans **Étape 4 Spécification de vos heures d’ouverture**, dans la zone **Votre fuseau horaire**, sélectionnez le fuseau horaire du flux de travail.
    
    > [!NOTE]
    > Il s’agit du fuseau horaire des appelants et des agents du flux de travail. Il est utilisé pour calculer les heures d’ouverture et de fermeture. Par exemple, si le flux de travail est configuré pour utiliser le fuseau horaire Est de l’Amérique du Nord et que l’ouverture et la fermeture du flux de travail sont planifiées respectivement pour 7 heures et 23 heures, il s’agit de l’heure d’ouverture 7:00 Est et de l’heure de fermeture 23:00 Est. (Vous devez entrer les heures au format 24 heures.) 
  
19. Sélectionnez le type d’heures d’ouverture à utiliser en effectuant l’une des opérations suivantes :
    
   - Pour utiliser un planning prédéfini d’heures d’ouverture, cliquez sur **Utiliser un planning prédéfini**, puis sélectionnez le planning souhaité dans la liste déroulante.
    
     > [!NOTE]
     > Pour sélectionner cette option, vous devez avoir défini précédemment au moins un planning prédéfini. Vous pouvez spécifier des plannings prédéfinis à l’aide de l’applet de commande **New-CSRgsHoursOfBusiness**. Pour plus d’informations, voir [heures (facultatif) définir Response Group dans Skype pour Business 2015](optional-define-response-group-business-hours.md). 
  
     > [!NOTE]
     > Lorsque vous sélectionnez un planning prédéfini, les champs **Jour**, **Ouverture** et **Fermeture** sont renseignés automatiquement avec les jours et les heures de disponibilité du groupe Response Group.
  
   - Pour utiliser un planning personnalisé qui ne s’applique qu’à ce flux de travail, cliquez sur **Utiliser un planning personnalisé**.
    
20. Si vous créez un planning personnalisé pour ce flux de travail, activez les cases à cocher correspondant aux jours de la semaine pendant lesquels le groupe Response Group est disponible.
    
21. Si vous créez un planning personnalisé, tapez les heures d’**ouverture** et de **fermeture** pour chaque jour de la semaine pendant lesquelles le groupe Response Group est disponible.
    
    > [!NOTE]
    > Les heures **Ouverture** et **Fermeture** doivent être au format 24 heures. Par exemple, si votre bureau est ouvert de 9 heures à 17 heures et fermé à midi pour le déjeuner, les heures d’ouverture sont spécifiées comme suit : **Ouverture** 9:00, **Fermeture** 12:00, **Ouverture** 13:00 et **Fermeture** 17:00.
  
22. Si vous souhaitez que la lecture d’un message se déclenche lorsque le bureau est fermé, activez la case à cocher **Lisez un message lorsque le service Response Group est en dehors des heures d’ouverture**, puis spécifiez le message à lire en effectuant l’une des opérations suivantes :
    
   - Pour entrer le message sous forme de texte converti en message vocal pour l’appelant, cliquez sur **Utiliser la synthèse vocale**, puis tapez le message dans la zone de texte.
    
     > [!NOTE]
     > N’incluez pas de balises HTML dans le texte que vous entrez. Si vous incluez des balises HTML, vous recevrez un message d’erreur. 
  
   - Pour utiliser un enregistrement de fichier audio pour le message, cliquez sur **Sélectionner un enregistrement**. Si vous souhaitez télécharger un nouveau fichier audio, cliquez sur le lien **un enregistrement**. Dans la nouvelle fenêtre de navigateur, cliquez sur **Parcourir**, sélectionnez le fichier à utiliser, puis cliquez sur **Ouvrir**. Cliquez sur **Télécharger** pour charger le fichier audio.
    
     > [!NOTE]
     > Tous les fichiers audio fournis aux utilisateurs doivent remplir certains critères. Pour plus d’informations sur les formats de fichiers audio pris en charge, voir [Configuration technique requise pour les groupes de réponses](http://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx). 
  
23. Spécifiez comment gérer les appels après la lecture du message (si un message est configuré) :
    
   - Pour déconnecter l’appel, cliquez sur **Déconnecter l’appel**.
    
   - Pour transférer l’appel vers la messagerie vocale, cliquez sur **Transférer à la messagerie vocale**, puis tapez l’adresse de la messagerie vocale. Le format de l’adresse de messagerie vocale est _ \<nom d’utilisateur\>_@ _\<domainName\> _ (par exemple, bob@contoso.com).
    
   - Pour transférer l’appel vers un autre utilisateur, cliquez sur **Transférer à l’URI SIP**, puis tapez l’adresse de l’utilisateur. Le format de l’adresse de l’utilisateur est _ \<nom d’utilisateur\>_@ _\<domainName\>_.
    
   - Pour transférer l’appel vers un autre numéro de téléphone, cliquez sur **Transférer au numéro de téléphone**, puis tapez le numéro de téléphone. Le format du numéro de téléphone est _ \<numéro\>_@ _\<domainName\> _ (par exemple, +14255550121@contoso.com). Le nom de domaine est utilisé pour router l’appelant vers la destination appropriée.
    
24. Dans **Étape 5 Spécification de vos congés**, activez les cases à cocher correspondant à une ou plusieurs périodes de congés définissant les jours de fermeture du groupe Response Group.
    
    > [!NOTE]
    > Vous devez définir les congés et les périodes de congé avant de configurer le flux de travail. Utilisez les applets de commande **New-CsRgsHoliday** et **New-CsRgsHolidaySet** pour créer des congés et des périodes de congé. Pour plus d’informations, voir [définir Response Group (facultatif) de congés dans Skype pour Business 2015](optional-define-response-group-holiday-sets.md). 
  
25. Si vous souhaitez que la lecture d’un message se déclenche pendant les congés, activez la case à cocher **Lisez un message pendant les congés**, puis spécifiez le message à lire en effectuant l’une des opérations suivantes :
    
  - Pour entrer le message sous forme de texte converti en message vocal pour l’appelant, cliquez sur **Utiliser la synthèse vocale**, puis tapez le message dans la zone de texte.
    
    > [!NOTE]
    > N’incluez pas de balises HTML dans le texte que vous entrez. Si vous incluez des balises HTML, vous recevrez un message d’erreur. 
  
   - Pour utiliser un enregistrement de fichier audio pour le message, cliquez sur **Sélectionner un enregistrement**. Si vous souhaitez télécharger un nouveau fichier audio, cliquez sur le lien **un enregistrement**. Dans la nouvelle fenêtre de navigateur, cliquez sur **Parcourir**, sélectionnez le fichier à utiliser, puis cliquez sur **Ouvrir**. Cliquez sur **Télécharger** pour charger le fichier audio.
    
     > [!NOTE]
     > Tous les fichiers audio fournis aux utilisateurs doivent remplir certains critères. Pour plus d’informations sur les formats de fichiers audio pris en charge, voir [Configuration technique requise pour les groupes de réponses](http://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx). 
  
26. Spécifiez comment gérer les appels après la lecture du message (si un message est configuré) :
    
   - Pour déconnecter l’appel, cliquez sur **Déconnecter l’appel**.
    
   - Pour transférer l’appel vers la messagerie vocale, cliquez sur **Transférer à la messagerie vocale**, puis tapez l’adresse de la messagerie vocale. Le format de l’adresse de messagerie vocale est _ \<nom d’utilisateur\>_@ _\<domainName\> _ (par exemple, bob@contoso.com).
    
   - Pour transférer l’appel vers un autre utilisateur, cliquez sur **Transférer à l’URI SIP**, puis tapez l’adresse de l’utilisateur. Le format de l’adresse de l’utilisateur est _ \<nom d’utilisateur\>_@ _\<domainName\>_.
    
   - Pour transférer l’appel vers un autre numéro de téléphone, cliquez sur **Transférer au numéro de téléphone**, puis tapez le numéro de téléphone. Le format du numéro de téléphone est _ \<numéro\>_@ _\<domainName\> _ (par exemple, +14255550121@contoso.com). Le nom de domaine est utilisé pour router l’appelant vers la destination appropriée.
    
27. Dans **Étape 6 Configuration d’une file d’attente**, dans **Sélectionnez la file d’attente qui reçoit les appels**, sélectionnez la file d’attente dans laquelle mettre les appelants en attendant qu’un agent soit disponible.
    
28. Dans **Étape 7 Configuration d’une attente musicale**, choisissez la musique que les appelants entendront pendant qu’ils attendent un agent. Pour cela, procédez de l’une des façons suivantes :
    
   - Pour utiliser l’enregistrement d’attente musicale par défaut, cliquez sur **Utiliser la valeur par défaut**.
    
   - Pour utiliser un enregistrement de fichier audio pour l’attente musicale, cliquez sur **Sélectionner un fichier de musique**. Si vous souhaitez télécharger un nouveau fichier audio, cliquez sur le lien **un fichier de musique**. Dans la nouvelle fenêtre de navigateur, cliquez sur **Parcourir**, sélectionnez le fichier à utiliser, puis cliquez sur **Ouvrir**. Cliquez sur **Télécharger** pour charger le fichier audio.
    
     > [!NOTE]
     > Tous les fichiers audio fournis aux utilisateurs doivent remplir certains critères. Pour plus d’informations sur les formats de fichiers audio pris en charge, voir [Configuration technique requise pour les groupes de réponses](http://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx). 
  
29. Cliquez sur **Déployer**.
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-hunt-group-workflow"></a>Utiliser Skype pour Business Server Management Shell pour créer ou modifier un flux de travail de groupe de recherche

1. Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre d’un des rôles d’administrateur prédéfinis qui prennent en charge Response Group.
    
2. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
3. Créez l’invite à exécuter pour le message de bienvenue, et enregistrez-la dans une variable. Dans la ligne de commande, exécutez la commande suivante :
    
   ```
   $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

    Exemple :
    
   ```
   $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "Welcome to Contoso. Please wait for an available agent."
   ```

     > [!NOTE]
     > Pour utiliser un fichier audio pour l’invite, utilisez la cmdlet **Import-CsRgsAudioFile** . Pour plus d’informations, voir [Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps). 
  
4. Obtenez l’identité de la file d’attente ou demandez où les appels seront dirigés. Dans la ligne de commande, exécutez la commande suivante :
    
   ```
   $qid = (Get-CsRgsQueue -Name "Help Desk").Identity
   ```

    Pour plus d’informations sur la création de la file d’attente, voir [New-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/new-csrgsqueue?view=skype-ps).
    
5. Définissez l’action par défaut à effectuer lorsqu’un flux de travail est ouvert pendant les heures ouvrées et enregistrez-la dans une variable. Dans la ligne de commande, exécutez la commande suivante :
    
   ```
   $actionWM = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken> -QueueID $qid
   ```

    > [!NOTE]
    > Pour les flux de travail de groupe de recherche, l’action par défaut doit rediriger l’appel vers une file d’attente. Ce paramètre est obligatoire pour les flux de travail actifs. Il ne l’est pas pour les flux de travail inactifs. 
  
    Exemple :
    
   ```
   $actionWM = New-CsRgsCallAction -Prompt $promptWM -Action TransferToQueue -QueueID $qid.Identity
   ```

6. Si vous voulez définir des heures ouvrées et des congés, vous devez les créer avant de créer et modifier le flux de travail. Pour plus d’informations, voir [heures (facultatif) définir Response Group dans Skype pour Business 2015](optional-define-response-group-business-hours.md) et [(facultatif) définir Response Group de congés dans Skype pour Business 2015](optional-define-response-group-holiday-sets.md).
    
7. Si vous souhaitez les invites pour les appels reçus en dehors des heures ou jours fériés, utilisez l’applet de commande **New-CsRgsPrompt** pour définir l’invite et la **New-CsRgsCallAction** permet de définir l’action à exécuter à l’invite. Pour plus d’informations, voir [New-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/new-csrgsprompt?view=skype-ps) et [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps).
    
8. Récupérer le nom de service pour le service Response Group Lync Server et l’assigner à une variable. Dans la ligne de commande, exécutez la commande suivante :
    
   ```
   $serviceId="service:"+(Get-CSService | ?{$_.Applications -like "*RGS*"}).ServiceId;
   ```

9. Créez ou modifiez le flux de travail. Pour créer un flux de travail, utilisez **New-CsRgsWorkflow**. Pour modifier un flux de travail, utilisez **La cmdlet Set-CsRgsWorkflow**. Dans la ligne de commande, tapez :
    
   ```
   $workflowHG = New-CsRgsWorkflow -Parent <service ID for the Response Group service> -Name "<hunt group name>" [-Description "<hunt group description>"] -PrimaryUri "<SIP address for the workflow>" [-LineUri "<Phone number for the workflow>"] [-DisplayNumber "<Phone number displayed in Lync>"] [-Active <$true | $false>] [-Anonymous <$true | $false>] [-DefaultAction <variable from preceding step>] [-EnabledForFederation <$true | $false>] [-Managed <$true | $false>] [-MangersByUri <SIP addresses for Response Group Managers who can manage the workflow>]
   ```

    Exemple :
    
   ```
   $workflowHG = New-CsRgsWorkflow -Parent $serviceID -Name "Human Resources" -Description "Human Resources workflow" -PrimaryUri "sip:humanresources@contoso.com" -LineUri "TEL:+14255551219" -DisplayNumber "555-1219" -Active $true -Anonymous $true -DefaultAction $actionWM -EnabledForFederation $false -Managed $true -ManagersByUri "sip:bob@contoso.com", "mindy@contoso.com"
   ```

     > [!IMPORTANT]
     > Tous les utilisateurs désignés comme responsables pour les flux de travail doivent posséder le rôle CsResponseGroupManager. 
  
     > [!NOTE]
     > Pour plus d’informations sur les paramètres facultatifs supplémentaires, voir [New-CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/new-csrgsworkflow?view=skype-ps) ou [Set-CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/set-csrgsworkflow?view=skype-ps)
  
## <a name="designing-an-interactive-workflow"></a>Conception d’un flux de travail interactif

Vous pouvez utiliser la réponse vocale interactive (IVR) pour obtenir des informations des appelants et acheminer l’appel jusqu’à la file d’attente appropriée. Les paires de questions et réponses déterminent la file d’attente à utiliser. Selon la réponse de l’appelant, l’appelant qu’entend une question de suivi ou est acheminé vers la file d’attente appropriée. Les questions à réponse vocale interactive et les réponses de l’appelant sont fournies à l’agent qui accepte l’appel, fournissant des informations précieuses à l’agent répond.
  
### <a name="overview-of-ivr-features"></a>Vue d’ensemble des fonctionnalités du système de réponse vocale interactive

L’application Response Group offre des fonctions vocales dans 26 langues et reconnaissance. Vous pouvez entrer les questions du système de réponse vocale interactive à l’aide de la conversion de texte par synthèse vocale, d’un fichier wave (.wav) ou d’un fichier audio Windows Media (.wma). Les appelants peuvent répondre à l’aide de la voix ou de réponses de numérotation en fréquences vocales (DTMF).
  
Flux de travail interactif prend en charge jusqu'à deux niveaux de questions, chaque question ayant quatre réponses possibles. La réponse vocale interactive demande à l’appelant une question et en fonction de la réponse de l’appelant, achemine l’appelant vers une file d’attente ou pose une deuxième question. La deuxième question peut également avoir des quatre réponses possibles. Selon la réponse à la question de second niveau, l’appelant est acheminé vers la file d’attente appropriée.
  
> [!NOTE]
> Lorsque vous concevez un flux d’appels à l’aide de Skype pour Business Server Management Shell, vous pouvez définir n’importe quel nombre de niveaux de questions de réponse vocale interactive et n’importe quel nombre de réponses. Cependant, pour faciliter l’utilisation par l’appelant, nous vous conseillons de vous limiter à trois niveaux de questions et cinq réponses par niveau. En outre, si vous concevez un flux d’appels ayant plus de deux niveaux de questions avec plus de quatre réponses chaque, vous ne pouvez pas modifier le flux des appels à l’aide de Skype pour le panneau de configuration serveur Business. 
  
Les questions à réponse vocale interactive et les réponses de l’appelant sont fournies à l’agent qui accepte l’appel répond.
  
### <a name="working-with-speech-technologies"></a>Utilisation des technologies vocales

Les technologies vocales, comme la reconnaissance vocale et la conversion de texte par synthèse vocale, peuvent améliorer le produit et permettre aux gens d’accéder plus naturellement et plus efficacement aux informations. Cependant, il peut arriver que le texte spécifié ou la réponse vocale de l’utilisateur ne soit pas reconnu correctement par le moteur de synthèse vocale. Par exemple, le moteur de synthèse vocale convertit le symbole « # » par le mot « numéro ». Ce problème peut être atténué en procédant comme suit :
  
- Le moteur de synthèse vocale autorise cinq tentatives de réponse. Si la réponse de l’appelant est incorrecte (autrement dit, si elle ne figure pas parmi les réponses spécifiées) ou s’il ne fournit aucune réponse, l’appelant a la possibilité de fournir la bonne réponse. L’appelant peut donner cinq réponses avant d’être déconnecté si aucune d’elles n’est correcte. Vous pouvez configurer le système de réponse vocale interactive de sorte qu’il lise un message personnalisé après chaque erreur de l’appelant. La question est répétée à chaque fois.
    
- Pour réduire le risque que le moteur de synthèse vocale interprète le bruit ambiant comme une réponse, utilisez des réponses plus longues. Par exemple, les réponses doivent comprendre plusieurs syllabes et être nettement différentes à l’oreille les unes des autres.
    
- Si vos questions présentent à la fois des réponses vocales et DTMF, configurez les réponses vocales en utilisant des mots qui représentent le concept plutôt que la réponse DTMF. Par exemple, plutôt que d’utiliser « Appuyez ou dites un », utilisez « Appuyez sur 1 ou dites facturation ».
    
- Après avoir conçu votre système de réponse vocale interactive, appelez le flux de travail, écoutez les invites, répondez à chacune d’elles à l’aide de la voix et vérifiez que le système de réponse vocale interactive se présente et se comporte comme prévu. Vous pouvez ensuite modifier le système de réponse vocale interactive afin de résoudre des problèmes liés à l’interprétation. Dans notre exemple précédent, si vous devez faire référence à la touche #, vous pouvez réécrire votre invite de réponse vocale interactive afin qu’elle utilise le nom de la touche au lieu du symbole #. Par exemple, « Pour être mis en relation avec le service commercial, appuyez sur la touche dièse ».
    
### <a name="ivr-design-examples"></a>Exemples de conception IVR

Les sections ci-dessous contiennent des exemples de différents scénarios de réponse vocale interactive et de paires de questions-réponses. 
  
#### <a name="ivr-with-one-level-of-questions"></a>Système de réponse vocale interactive avec un niveau de questions

L’exemple ci-dessous illustre un système de réponse vocale interactive utilisant un niveau de questions. Il utilise la reconnaissance vocale pour détecter la réponse de l’appelant.
  
 **Question :** « Merci d’appeler le service des ressources humaines. Si vous souhaitez parler à une personne de l’équipe qui traite les salaires, dites salaire. Autrement, dites RH. »
  
- **L’option 1 est sélectionnée :** l’appelant est dirigé vers l’équipe qui s’occupe des salaires.
    
- **L’option 2 est sélectionnée :** l’appelant est dirigé vers l’équipe des ressources humaines.
    
L’illustration ci-dessous montre le flux d’appels.
  
 **Flux d’appels pour un modèle interactif à un niveau**
  
![Concevoir des flux d’appels à l’aide du système de réponse vocale interactive](../../media/Ops_OCS_RGS_IVRLevel1.jpg)
  
#### <a name="ivr-with-two-levels-of-questions"></a>Système de réponse vocale interactive avec deux niveaux de questions

L’exemple ci-dessous illustre un système de réponse vocale interactive utilisant deux niveaux de questions. Il permet aux appelants de répondre à l’aide de la voix ou de la numérotation en fréquences vocales (DTMF).
  
 **Question :** « Merci d’appeler le support technique informatique. Si vous rencontrez un problème d’accès réseau, appuyez sur 1 ou dites « réseau ». Si vous rencontrez un problème de logiciel, appuyez sur 2 ou dites « logiciel ». Si vous rencontrez un problème de matériel, appuyez sur 3 ou dites « matériel ». »
  
- **L’option 1 est sélectionnée :** l’appelant est dirigé vers l’équipe de gestion du réseau.
    
- **L’option 2 est sélectionnée :** une question de suivi est posée à l’appelant :
    
    **Question :** « S’il s’agit d’un problème lié au système d’exploitation, appuyez sur 1 ou dites « système d’exploitation ». S’il s’agit d’un problème avec une application interne, appuyez sur 2 ou dites « application interne ». Autrement, appuyez sur 3 ou dites « autre ». »
    
  - **L’option 1 est sélectionnée :** l’appelant est dirigé vers l’équipe de support des systèmes d’exploitation.
    
  - **L’option 2 est sélectionnée :** l’appelant est dirigé vers l’équipe de support des applications internes.
    
  - **L’option 3 est sélectionnée :** l’appelant est dirigé vers l’équipe de support des logiciels.
    
- **L’option 3 est sélectionnée :** une question de suivi est posée à l’appelant :
    
    **Question :** « S’il s’agit d’un problème d’imprimante, appuyez sur 1. Autrement, appuyez sur 2. »
    
  - **L’option 1 est sélectionnée :** l’appelant est dirigé vers l’équipe de support des imprimantes.
    
  - **L’option 2 est sélectionnée :** l’appelant est dirigé vers l’équipe de support du matériel.
    
L’illustration ci-dessous présente le flux d’appels.
  
 **Flux d’appels pour un modèle interactif à deux niveaux**
  
![Concevoir des flux d’appels à l’aide du système de réponse vocale interactive](../../media/Ops_OCS_RGS_IVRLevel2.jpg)
  
### <a name="best-practices"></a>Meilleures pratiques

La liste ci-dessous décrit certaines meilleures pratiques lorsque vous concevez votre système de réponse vocale interactive :
  
- Permettez à l’appelant d’accéder rapidement à la tâche. Évitez de mettre trop d’informations ou de longs messages marketing dans votre système de réponse vocale interactive.
    
- Si vous souhaitez inclure un long message, envisagez de l’intégrer à la première question plutôt qu’au message d’accueil. Les appelant peuvent contourner le message s’il fait partie de la première question en répondant à la question, mais ils ne peuvent pas contourner le message d’accueil.
    
- Parlez dans la langue de l’appelant. Évitez le langage emprunté. Parlez naturellement.
    
- Écrivez des invites efficaces. Supprimez toutes les options inutiles. Structurez les informations afin que la réponse attendue de l’appelant est à la fin de la phrase. Par exemple, « pour parler à l’équipe commerciale, appuyez sur 1. »
    
- Rendez les réponses vocales conviviales pour l’appelant. Par exemple, si vous spécifiez des réponses vocales et DTMF, utilisez, par exemple : « Pour parler à l’équipe commerciale, appuyez sur 1 ou dites commercial. »
    
- Testez le système de réponse vocale interactive sur un groupe d’utilisateurs avant de le déployer dans votre organisation.
    
## <a name="creating-or-modifying-an-interactive-workflow"></a>Création ou modification d’un flux de travail interactif

### <a name="to-use-response-group-configuration-tool-to-create-or-modify-an-interactive-workflow"></a>Pour utiliser l’outil de Configuration pour Response Group pour créer ou modifier un workflow interactif

1. Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre d’un des rôles d’administrateur prédéfinis qui prennent en charge Response Group.
    
2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.  
    
3. Dans la barre de navigation de gauche, cliquez sur **Services Response Group**, puis sur **Flux de travail**.
    
4. Dans la page **Flux de travail**, cliquez sur **Créer ou modifier un flux de travail**.
    
5. Dans le champ **Sélectionner un Service** de recherche, tapez entièrement ou partiellement le nom du service **ApplicationServer** qui héberge le flux de travail que vous souhaitez créer ou modifier. Dans la liste de services qui s’affiche, cliquez sur le service de votre choix, puis sur **OK**.
    
    > [!NOTE]
    > L’outil de Configuration Response Group s’ouvre. Vous pouvez également ouvrir l’outil de Configuration Response Group directement à partir d’un navigateur web en tapant l’URL suivante : https:// _ \<webPoolFqdn\>_/RgsConfig. 
  
6. Effectuez l’une des actions suivantes :
    
   - Sous **Créer un flux de travail**, en regard de **Interactif**, cliquez sur **Créer**.
    
   - Sous **Gérer un flux de travail existant**, recherchez le flux de travail à modifier, puis sous **Action**, cliquez sur **Modifier**.
    
7. Si vous n’êtes pas prêt et que les utilisateurs ne peuvent pas encore commencer à appeler le flux de travail, décochez la case **Activer le flux de travail**.
    
    > [!NOTE]
    >  Si vous créez un flux de travail géré, vous devez sélectionner **Activer le flux de travail**. Une fois le flux de travail géré actif enregistré, vous pouvez le modifier et le désactiver. 
  
8. Pour autoriser les utilisateurs fédérés à appeler le groupe, activez la case à cocher **Activer pour la fédération**. Vous devez également disposer d’une stratégie d’accès externe qui s’applique à l’application Response Group configurée pour la fédération.
    
    > [!NOTE]
    > La stratégie d’accès externe globale s’applique à l’application Response Group. Vous pouvez configurer la stratégie globale pour la fédération de groupe de réponse à l’aide de Skype pour le panneau de configuration serveur Business ou à l’aide de l’applet de commande **Set-CsExternalAccessPolicy** pour définir le paramètre EnableOutsideAccess sur True. Gardez à l’esprit que les paramètres de stratégie globale s’appliquent à tous les utilisateurs sauf s’ils sont affectés à un site ou une stratégie d’utilisateur. Par conséquent, avant de modifier ce paramètre pour les groupes Response Group, assurez-vous que le paramètre de fédération satisfait les exigences de votre organisation. Pour plus d’informations sur comment appliquent des stratégies pour les utilisateurs, voir [Gestion d’une stratégie d’accès externe pour votre organisation](http://technet.microsoft.com/library/5571811e-34c8-443a-b94c-1ab5d4275581.aspx). Pour plus d’informations sur le paramètre de fédération, voir **Set-CsExternalAccessPolicy** dans la documentation...
  
    > [!NOTE]
    > Les utilisateurs qui sont hébergées dans Skype pour Business Online ne peuvent pas passer des appels à des groupes de réponses qui sont hébergées dans un déploiement sur site. Cela est vrai dans les deux déploiements hybrides et dans les cas où un déploiement sur site est fédéré avec une Skype pour le déploiement d’entreprise en ligne. 
  
9. Pour masquer l’identité des agents pendant les appels, activez la case à cocher **Activer l’anonymat de l’agent**.
    
    > [!NOTE]
    > Les appels anonymes ne peuvent pas commencer par la messagerie instantanée ou la vidéo, mais l’agent ou l’appelant peut ajouter la messagerie instantanée et la vidéo une fois que l’appel a commencé. Un agent anonyme peut également mettre des appels en attente, transférer des appels (transferts invisibles et consultatifs), mais aussi parquer et récupérer des appels. Les appels anonymes ne prennent pas en charge la conférence, le partage d’application, le partage du Bureau, le transfert de fichiers, le tableau blanc, la collaboration de données et l’enregistrement d’appel. Les agents utilisant le plugin Lync VDI peuvent recevoir des appels entrants anonymes, mais ils ne peuvent pas effectuer d’appels sortants anonymes. 
  
10. Sous **Entrez l’adresse du groupe qui recevra les appels**, cliquez sur l’adresse URI SIP (Session Initiation Protocol) principale du groupe qui doit prendre les appels vers le flux de travail.
    
11. Dans **Nom d’affichage**, tapez le nom que vous souhaitez afficher pour le flux de travail (par exemple, Sales IVR Response Group).
    
    > [!NOTE]
    > N’incluez pas le «\<« ou »\>» caractères dans le nom complet. N’utilisez pas les noms d’affichage ci-dessous, car ils sont réservés : RGS Presence Watcher ou Service d’annonce. 
  
12. Dans **Numéro de téléphone**, tapez l’URI de ligne pour le groupe Response Group (par exemple, +14255550165).
    
13. Dans **Numéro affiché**, tapez le numéro tel qu’il doit s’afficher pour le groupe Response Group (par exemple, +1 (425) 555-0165).
    
14. (Facultatif) Dans la zone **Description**, tapez une description pour le flux de travail que vous souhaitez voir apparaître sur la carte de visite dans Skype pour les entreprises. 
    
15. Dans **Type de flux de travail**, sélectionnez **Géré** si ce flux de travail sera géré par un responsable de groupes Response Group. Procédez comme suit pour affecter des responsables de groupe de réponse pour le flux de travail :
    
    a. Tapez l’URI SIP (Session Initiation Protocol) d’un responsable pour ce flux de travail, puis cliquez sur **Ajouter**.
    
    b. Tapez l’URI SIP (Session Initiation Protocol) d’autres responsables à ajouter au flux de travail, puis cliquez sur **Ajouter**.
    
    > [!IMPORTANT]
    > Tous les utilisateurs désignés comme responsables d’un groupe Response Group doivent posséder le rôle CsResponseGroupManager. Si les utilisateurs n’ont pas ce rôle, ils ne peuvent pas gérer les groupes Response Group. 
  
16. Dans **Étape 2 Sélection d’une langue**, cliquez sur la langue à utiliser pour la reconnaissance vocale et la synthèse vocale.
    
17. Si vous souhaitez configurer un message de bienvenue, dans **Étape 3 Configuration d’un message de bienvenue**, activez la case à cocher **Lisez un message de bienvenue**, puis effectuez l’une des opérations suivantes :
    
    - Pour entrer le message de bienvenue sous forme de texte converti en message vocal pour les appelants, cliquez sur **Utiliser la synthèse vocale**, puis tapez le message de bienvenue dans la zone de texte.
    
    > [!NOTE]
    > N’incluez pas de balises HTML dans le texte que vous entrez. Si vous incluez des balises HTML, vous recevrez un message d’erreur. 
  
    - Pour utiliser un enregistrement au format de fichier Wave ou Windows Media Audio pour le message de bienvenue, cliquez sur **Sélectionner un enregistrement**. Si vous souhaitez télécharger un nouveau fichier audio, cliquez sur le lien **un enregistrement**. Dans la nouvelle fenêtre de navigateur, cliquez sur **Parcourir**, sélectionnez le fichier audio à utiliser, puis cliquez sur **Ouvrir**. Cliquez sur **Télécharger** pour charger le fichier audio.
    
    > [!NOTE]
    > Tous les fichiers audio fournis aux utilisateurs doivent remplir certains critères. Pour plus d’informations sur les formats de fichiers pris en charge, voir [Configuration technique requise pour les groupes de réponses](http://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx). 
  
18. Dans **Étape 4 Indication de vos heures d’ouverture**, dans la zone **Votre fuseau horaire**, cliquez sur le fuseau horaire du flux de travail.
    
    > [!NOTE]
    > Il s’agit du fuseau horaire des appelants et des agents du flux de travail. Il est utilisé pour calculer les heures d’ouverture et de fermeture. Par exemple, si le flux de travail est configuré pour utiliser le fuseau horaire Est de l’Amérique du Nord et que l’ouverture et la fermeture du flux de travail sont planifiées respectivement pour 7 heures et 23 heures, il s’agit de l’heure d’ouverture 7:00 Est et de l’heure de fermeture 11:00 Est. (Vous devez entrer les heures au format 24 heures.) 
  
19. Sélectionnez le type d’heures d’ouverture à utiliser en effectuant l’une des opérations suivantes :
    
   - Pour utiliser un planning prédéfini d’heures d’ouverture, cliquez sur **Utiliser un planning prédéfini**, puis sélectionnez le planning souhaité dans la liste déroulante.
    
     > [!NOTE]
     > Pour sélectionner cette option, vous devez avoir défini précédemment au moins un planning prédéfini. Vous pouvez spécifier des plannings prédéfinis à l’aide de l’applet de commande **New-CSRgsHoursOfBusiness**. Pour plus d’informations, voir [heures (facultatif) définir Response Group dans Skype pour Business 2015](optional-define-response-group-business-hours.md). Lorsque vous sélectionnez un planning prédéfini, les champs **Jour**, **Ouverture** et **Fermeture** sont renseignés automatiquement avec les jours et les heures de disponibilité du groupe Response Group.
  
   - Pour utiliser un planning personnalisé qui ne s’applique qu’à ce flux de travail, cliquez sur **Utiliser un planning personnalisé**.
    
20. Si vous créez un planning personnalisé pour ce flux de travail, activez les cases à cocher correspondant aux jours de la semaine pendant lesquels le groupe Response Group est disponible.
    
21. Si vous créez un planning personnalisé, tapez les heures **Ouverture** et **Fermeture** auxquelles le groupe Response Group est disponible.
    
     > [!NOTE]
     > Les heures **Ouverture** et **Fermeture** doivent être au format 24 heures. Par exemple, si votre bureau est ouvert de 9 heures à 17 heures et fermé à midi pour le déjeuner, les heures d’ouverture sont spécifiées comme suit : **Ouverture** 9:00, **Fermeture** 12:00, **Ouverture** 13:00 et **Fermeture** 17:00.
  
22. Si vous souhaitez que la lecture d’un message se déclenche lorsque le bureau est fermé, activez la case à cocher **Lisez un message lorsque le service Response Group est en dehors des heures d’ouverture**, puis spécifiez le message à lire en effectuant l’une des opérations suivantes :
    
    - Pour entrer le message sous forme de texte converti en message vocal pour l’appelant, cliquez sur **Utiliser la synthèse vocale**, puis tapez le message dans la zone de texte.
    
     > [!NOTE]
     > N’incluez pas de balises HTML dans le texte que vous entrez. Si vous incluez des balises HTML, vous recevrez un message d’erreur. 
  
    - Pour utiliser un enregistrement de fichier audio pour le message, cliquez sur **Sélectionner un enregistrement**. Si vous souhaitez télécharger un nouveau fichier audio, cliquez sur le lien **un enregistrement**. Dans la nouvelle fenêtre de navigateur, cliquez sur **Parcourir**, sélectionnez le fichier à utiliser, puis cliquez sur **Ouvrir**. Cliquez sur **Télécharger** pour charger le fichier audio.
    
    > [!NOTE]
    > Tous les fichiers audio fournis aux utilisateurs doivent remplir certains critères. Pour plus d’informations sur les formats de fichiers pris en charge, voir [Configuration technique requise pour les groupes de réponses](http://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx). 
  
23. Spécifiez comment gérer les appels après la lecture du message (si un message est configuré) :
    
     - Pour déconnecter l’appel, cliquez sur **Déconnecter l’appel**.
    
     - Pour transférer l’appel vers la messagerie vocale, cliquez sur **Transférer à la messagerie vocale**, puis tapez l’adresse de la messagerie vocale. Le format de l’adresse de messagerie vocale est _ \<nom d’utilisateur\>_@ _\<domainname\> _ (par exemple, bob@contoso.com).
    
     - Pour transférer l’appel vers un autre utilisateur, cliquez sur **Transférer à l’URI SIP**, puis tapez l’adresse de l’utilisateur. Le format de l’adresse de l’utilisateur est _ \<nom d’utilisateur\>_@ _\<domainname\>_.
    
     - Pour transférer l’appel vers un autre numéro de téléphone, cliquez sur **Transférer au numéro de téléphone**, puis tapez le numéro de téléphone. Le format du numéro de téléphone est _ \<numéro\>_@ _\<domainname\> _ (par exemple, +14255550121@contoso.com). Le nom de domaine est utilisé pour router l’appelant vers la destination appropriée.
    
24. Dans **Étape 5 Spécification de vos congés**, activez les cases à cocher correspondant à une ou plusieurs périodes de congés définissant les jours de fermeture du groupe Response Group.
    
    > [!NOTE]
    > Vous devez définir les congés et les périodes de congé avant de configurer le flux de travail. Utilisez les applets de commande **New-CsRgsHoliday** et **New-CsRgsHolidaySet** pour créer des congés et des périodes de congé. Pour plus d’informations, voir [définir Response Group (facultatif) de congés dans Skype pour Business 2015](optional-define-response-group-holiday-sets.md). 
  
25. Si vous souhaitez que la lecture d’un message se déclenche pendant les congés, activez la case à cocher **Lisez un message pendant les congés**, puis spécifiez le message à lire en effectuant l’une des opérations suivantes :
    
   - Pour entrer le message sous forme de texte converti en message vocal pour l’appelant, cliquez sur **Utiliser la synthèse vocale**, puis tapez le message dans la zone de texte.
    
     > [!NOTE]
     > N’incluez pas de balises HTML dans le texte que vous entrez. Si vous incluez des balises HTML, vous recevrez un message d’erreur. 
  
   - Pour utiliser un enregistrement de fichier audio pour le message, cliquez sur **Sélectionner un enregistrement**. Si vous souhaitez télécharger un nouveau fichier audio, cliquez sur le lien **un enregistrement**. Dans la nouvelle fenêtre de navigateur, cliquez sur **Parcourir**, sélectionnez le fichier à utiliser, puis cliquez sur **Ouvrir**. Cliquez sur **Télécharger** pour charger le fichier audio.
    
     > [!NOTE]
     > Tous les fichiers audio fournis aux utilisateurs doivent remplir certains critères. Pour plus d’informations sur les formats de fichiers audio pris en charge, voir [Configuration technique requise pour les groupes de réponses](http://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx). 
  
26. Spécifiez comment gérer les appels après la lecture du message (si un message est configuré) :
    
    - Pour déconnecter l’appel, cliquez sur **Déconnecter l’appel**.
    
    - Pour transférer l’appel vers la messagerie vocale, cliquez sur **Transférer à la messagerie vocale**, puis tapez l’adresse de la messagerie vocale. Le format de l’adresse de messagerie vocale est _ \<nom d’utilisateur\>_@ _\<domainname\> _ (par exemple, bob@contoso.com).
    
    - Pour transférer l’appel vers un autre utilisateur, cliquez sur **Transférer à l’URI SIP**, puis tapez l’adresse de l’utilisateur. Le format de l’adresse de l’utilisateur est _ \<nom d’utilisateur\>_@ _\<domainname\>_.
    
    - Pour transférer l’appel vers un autre numéro de téléphone, cliquez sur **Transférer au numéro de téléphone**, puis tapez le numéro de téléphone. Le format du numéro de téléphone est _ \<numéro\>_@ _\<domainname\> _ (par exemple, +14255550121@contoso.com). Le nom de domaine est utilisé pour router l’appelant vers la destination appropriée.
    
27. Dans **Étape 6 Configuration d’une attente musicale**, indiquez ce que les appelants doivent entendre pendant qu’ils attendent un agent. Pour cela, procédez de l’une des façons suivantes :
    
    - Pour utiliser l’enregistrement d’attente musicale par défaut, cliquez sur **Utiliser la valeur par défaut**.
    
    - Pour utiliser un enregistrement audio pour l’attente musicale, cliquez sur **Sélectionner un fichier de musique**. Si vous souhaitez télécharger un nouveau fichier audio, cliquez sur le lien **un fichier de musique**. Dans la nouvelle fenêtre de navigateur, cliquez sur **Parcourir**, sélectionnez le fichier à utiliser, puis cliquez sur **Ouvrir**. Cliquez sur **Télécharger** pour charger le fichier audio.
    
    > [!NOTE]
    > Tous les fichiers audio fournis aux utilisateurs doivent remplir certains critères. Pour plus d’informations sur les formats de fichiers pris en charge, voir [Configuration technique requise pour les groupes de réponses](http://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx). 
  
28. Dans **Étape 7 Configuration de la réponse vocale interactive**, dans l’en-tête **L’utilisateur entendra le texte ou message enregistré suivant**, spécifiez la question à poser aux appelants :
    
    - Pour entrer la question au format texte, cliquez sur **Utiliser la synthèse vocale**, puis tapez la question dans la zone de texte.
    
    > [!NOTE]
    > N’incluez pas de balises HTML dans le texte que vous entrez. Si vous incluez des balises HTML, vous recevrez un message d’erreur. 
  
    > [!NOTE]
    > Le moteur de synthèse vocale convertit le symbole « # » par le mot « numéro ». Pour faire référence à la touche #, utilisez le nom de celle-ci au lieu de son symbole dans votre message d’invite. Par exemple, « Pour être mis en relation avec le service commercial, appuyez sur la touche dièse ». 
  
   - Pour utiliser un fichier audio préenregistré contenant la question, cliquez sur **Sélectionner un enregistrement**, puis cliquez sur le lien **un enregistrement** pour télécharger le fichier. Dans la nouvelle fenêtre de navigateur, cliquez sur **Parcourir**, sélectionnez le fichier audio, puis cliquez sur **Ouvrir**. Cliquez sur **Télécharger** pour charger le fichier, puis vous pouvez taper la question dans la zone de texte (Cela permet la question et réponse de l’appelant, à transmettre à l’agent qui répond).
    
     > [!NOTE]
     > Tous les fichiers audio fournis aux utilisateurs doivent remplir certains critères. Pour plus d’informations sur les formats de fichiers pris en charge, voir [Configuration technique requise pour les groupes de réponses](http://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx). 
  
29. Dans **Réponse 1**, spécifiez la première réponse possible à la question, comme suit :
    
    > [!IMPORTANT]
    > N’incluez pas de guillemets (") dans les réponses vocales. Les guillemets entraînent l’échec de la réponse vocale interactive (IVR). 
  
    > [!NOTE]
    > Vous pouvez choisir d’autoriser les appelants à répondre vocalement et/ou au clavier. 
  
    - Si vous souhaitez permettre à l’appelant de répondre vocalement, entrez la réponse dans **Entrer une réponse vocale**.
    
    - Pour permettre à l’appelant de répondre en appuyant sur une touche du pavé numérique, dans **Chiffre**, cliquez sur le chiffre du pavé numérique.
    
30. Spécifiez si l’appelant doit être redirigé vers une file d’attente ou si une autre question doit être posée. À cet effet, procédez comme suit :
    
    - Pour rediriger l’appelant vers une file d’attente, cliquez sur **Envoyer vers une file d’attente** et, dans **Sélectionner une file d’attente**, cliquez sur la file d’attente à utiliser.
    
    - Pour poser une autre question, cliquez sur **Poser une autre question**, puis cliquez sur **Utiliser la synthèse vocale** et tapez la question ou cliquez sur **Sélectionner un enregistrement**. Utilisez les regroupements de réponses de cette section pour spécifier jusqu’à quatre réponses possibles à la question supplémentaire, ainsi que la file d’attente à utiliser pour chaque réponse. Pour spécifier une troisième ou quatrième réponse possible, cochez la case **Réponse 3** ou **Réponse 4**.
    
31. Spécifiez jusqu’à trois autres réponses possibles à la question d’origine en répétant les étapes 28 et 29, pour indiquer les réponses possibles et l’action à effectuer pour chaque réponse. Pour spécifier une troisième ou quatrième réponse possible, cochez la case **Réponse 3** ou **Réponse 4**.
    
32. Cliquez sur **Déployer**.
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-an-interactive-workflow"></a>Utiliser Skype pour Business Server Management Shell pour créer ou modifier un workflow interactif

1.  Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre d’un des rôles d’administrateur prédéfinis qui prennent en charge Response Group.
    
2. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
3. Extrayez le nom de service du service Response Group et affectez-le à une variable. À partir de la ligne de commande, exécutez la commande suivante :
    
   ```
   $serviceId="service:"+(Get-CSService | ?{$_.Applications -like "*RGS*"}) .ServiceId;
   ```

4. Un flux de travail interactif nécessite au moins deux files d’attente et plusieurs groupes d’agents. Commencez par créer les groupes d’agents. Exécutez le code suivant :
    
   ```
   $AGSupport = New-CsRgsAgentGroup -Parent $serviceId -Name "Technical Support" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:agent1@contoso.com", "sip:agent2@contoso.com")]
   $AGSales = New-CsRgsAgentGroup -Parent $serviceId -Name "Sales Team" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:bob@contoso.com", "sip:alice@contoso.com")]
   ```

5. Créez des files d’attente. Exécutez :
    
   ```
   $QSupport = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Support" -AgentGroupIDList($AG-Support.Identity)
   $QSales = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Sales" -AgentGroupIDList($AG-Sales.Identity)
   ```

6. Créez la première invite Response Group. Exécutez le code suivant :
    
   ```
   $SupportPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please be patient while we connect you with Contoso Technical Support."
   ```

7. Créez ensuite l’action à effectuer après l’invite. Exécutez le code suivant :
    
   ```
   $SupportAction = New-CsRgsCallAction -Prompt $SupportPrompt -Action TransferToQueue -QueueID $QSupport.Identity
   ```

8. Créez la première réponse Response Group. Exécutez le code suivant :
    
   ```
   $SupportAnswer = New-CsRgsAnswer -Action $SupportAction [-DtmfResponse 1]
   ```

9. Créez maintenant les deuxièmes invite, action d’appel et réponse. Créez d’abord l’invite. Exécutez le code suivant :
    
   ```
   $SalesPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please hold while we connect you with Contoso Sales."
   ```

10. Créez la deuxième action d’appel. Exécutez le code suivant :
    
    ```
    $SalesAction = New-CsRgsCallAction -Prompt $SalesPrompt -Action TransferToQueue -QueueID $QSales.Identity
    ```

11. Créez la deuxième réponse Response Group. Exécutez le code suivant :
    
    ```
    $SalesAnswer = New-CsRgsAnswer -Action $SalesAction [-DtmfResponse 2]
    ```

12. Créez l’invite de niveau supérieur. Exécutez :
    
    ```
    $TopLevelPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Thank you for calling Contoso. For Technical Support, press 1. For a Sales Representative, press 2."
    ```

13. Créez la question de niveau supérieur. Exécutez :
    
    ```
    $TopLevelQuestion = New-CsRgsQuestion -Prompt $TopLevelPrompt [-AnswerList ($SupportAnswer, $SalesAnswer)]
    ```

14. Créez maintenant le flux de travail. Exécutez :
    
    ```
    $IVRAction = New-CsRgsCallAction -Action TransferToQuestion [-Question $Question]
    $IVRWorkflow = New-CsRgsWorkflow -Parent $ServiceId -Name "Contoso Helpdesk" [-Description "The Contoso Helpdesk line."] -PrimaryUri "sip:helpdesk@contoso.com" [-LineUri tel:+14255554321] [-DisplayNumber "+1 (425) 555-4321"] [-Active $true] [-Anonymous $true] [-DefaultAction $IVRAction] [-Managed $true] [-ManagersByURI ("sip:mindy@contoso.com", "sip:bob@contoso.com")]
    ```

     > [!NOTE]
     > Tous les utilisateurs désignés comme responsables d’un groupe Response Group doivent posséder le rôle CsResponseGroupManager qui leur est affecté. Dans le cas contraire, ils ne peuvent pas gérer de groupe Response Group. 
  
## <a name="see-also"></a>Voir aussi

#### 

[(Facultatif) Définir Response Group de congés dans Skype pour Business 2015](optional-define-response-group-holiday-sets.md)

[(Facultatif) Groupe de réponse de définir les heures d’ouverture Skype pour Business 2015](optional-define-response-group-business-hours.md)

[New-CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/new-csrgsworkflow?view=skype-ps)
  
[Set-CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/set-csrgsworkflow?view=skype-ps)
  
[New-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/new-csrgsprompt?view=skype-ps)
  
[New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps)

