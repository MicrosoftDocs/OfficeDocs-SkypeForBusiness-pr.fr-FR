---
title: 'Lync Server 2013 : création ou modification d’un flux de travail interactif'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify an interactive workflow
ms:assetid: bc7bb1bc-bf6a-4636-ae93-c56fa22613fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205213(v=OCS.15)
ms:contentKeyID: 48185260
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 93df8640593769b7b90d8b4e157133f8f7df2f19
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "41994079"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-an-interactive-workflow-in-lync-server-2013"></a>Création ou modification d’un flux de travail interactif dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-09-11_

En choisissant l’une des procédures suivantes, vous pouvez créer ou modifier un flux de travail interactif.

<div>


> [!NOTE]  
> Vous pouvez utiliser Lync Server Management Shell ou l’outil de configuration Response Group pour créer et modifier des flux de travail interactifs. Vous pouvez accéder à l’outil de configuration Response Group à partir du panneau de configuration de Lync Server ou en ouvrant la page Web directement à partir d’un navigateur Web en tapant l’URL suivante : <STRONG>https://</STRONG>&lt;webpoolfqdn représente&gt;<STRONG>/RgsConfig</STRONG>.



</div>

<div>

## <a name="to-use-response-group-configuration-tool-to-create-or-modify-an-interactive-workflow"></a>Pour utiliser l’outil de configuration de Response Group pour créer ou modifier un flux de travail interactif

1.  Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre d’un des rôles d’administration prédéfinis prenant en charge Response Group.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Groupes Response Group**, puis sur **Flux de travail**.

4.  Sur la page **Flux de travail**, cliquez sur **Créer ou modifier un flux de travail**.

5.  Dans le champ de recherche **Sélectionner un service**, tapez entièrement ou partiellement le nom du service **ApplicationServer** qui héberge le flux de travail à créer ou à modifier. Dans la liste des services obtenue, cliquez sur le service de votre choix, puis sur **OK**.
    
    <div>
    

    > [!NOTE]  
    > L’outil de configuration Response Group s’ouvre. Vous pouvez également ouvrir l’outil de configuration Response Group directement à partir d’un navigateur Web en tapant l’URL suivante : <STRONG>https://</STRONG>&lt;webpoolfqdn représente&gt;<STRONG>/RgsConfig</STRONG>.

    
    </div>

6.  Effectuez l’une des actions suivantes :
    
      - Sous **Créer un flux de travail**, à côté de **Interactif**, cliquez sur **Créer**.
    
      - Sous **Gérer un flux de travail existant**, recherchez le flux de travail que vous souhaitez modifier, puis sous **Action**, cliquez sur **Modifier**.

7.  Si vous n’êtes pas prêt et que les utilisateurs ne peuvent pas encore commencer à appeler le flux de travail, décochez la case **Activer le flux de travail**.
    
    <div>
    

    > [!NOTE]  
    > Si vous devez créer un flux de travail géré, sélectionnez <STRONG>Activer le flux de travail</STRONG>. Une fois le flux de travail géré actif enregistré, vous pouvez ensuite le modifier et le désactiver.

    
    </div>

8.  Pour autoriser les utilisateurs fédérés à appeler le groupe, activez la case à cocher **Activer pour la fédération**. Vous devez également disposer d’une stratégie d’accès externe qui s’applique à l’application Response Group configurée pour la Fédération.
    
    <div>
    

    > [!NOTE]  
    > La stratégie d’accès externe globale s’applique à l’application Response Group. Vous pouvez configurer la stratégie globale pour la Fédération Response Group à l’aide du panneau de configuration Lync Server ou à l’aide de la cmdlet <STRONG>Set-CsExternalAccessPolicy</STRONG> pour définir le paramètre EnableOutsideAccess sur true. Gardez à l’esprit que les paramètres de stratégie globale s’appliquent à tous les utilisateurs sauf s’ils se voient affectés un site ou une stratégie utilisateur. Par conséquent, avant de modifier ce paramètre pour les groupes Response Group, assurez-vous que le paramètre de fédération satisfait les exigences de votre organisation. Pour plus d’informations sur l’application des stratégies aux utilisateurs, consultez la rubrique <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">gestion de la stratégie d’accès externe dans Lync Server 2013</A>. Pour plus d’informations sur le paramètre de Fédération, voir <STRONG>Set-CsExternalAccessPolicy</STRONG> dans la documentation de Lync Server Management Shell.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Les utilisateurs hébergés dans Lync Online ne peuvent pas passer d’appels à des groupes Response Group qui sont hébergés dans un déploiement local. Cela est vrai dans les déploiements hybrides et dans les cas où un déploiement sur site est fédéré avec un déploiement Lync Online.

    
    </div>

9.  Pour masquer l’identité des agents pendant les appels, activez la case à cocher **Activer l’anonymat de l’agent**.
    
    <div>
    

    > [!NOTE]  
    > Les appels anonymes ne peuvent pas démarrer avec la messagerie instantanée ou la vidéo, mais l’agent ou l’appelant peut ajouter la messagerie instantanée et la vidéo une fois que l’appel a commencé. Un agent anonyme peut aussi mettre des appels en attente, transférer des appels (transferts invisibles et consultatifs), mais aussi parquer et récupérer des appels. Les appels anonymes ne prennent pas en charge la conférence, le partage d’application, le partage du Bureau, le transfert de fichiers, le tableau blanc, la collaboration de données et l’enregistrement d’appel. Les agents utilisant le plug-in Lync VDI peuvent recevoir des appels entrants de manière anonyme, mais ils ne peuvent pas passer des appels sortants de manière anonyme.

    
    </div>

10. Sous **Entrez l’adresse du groupe qui recevra les appels**, cliquez sur l’adresse URI (Uniform Resource Identifier) du domaine SIP principal du groupe qui doit répondre aux appels pour le flux de travail.

11. Dans **Nom d’affichage**, tapez le nom que vous souhaitez voir s’afficher pour le flux de travail (par exemple, Sales IVR Response Group).
    
    <div>
    

    > [!NOTE]  
    > N’incluez pas les&lt;caractères « »&gt;ou « » dans le nom d’affichage. N’utilisez pas les noms d’affichage suivants, car ils sont réservés : RGS Presence Watcher ou Service d’annonce.

    
    </div>

12. Dans **Numéro de téléphone**, tapez L’URI de ligne pour le groupe Response Group (par exemple, +14255550165).

13. Dans **Numéro affiché**, tapez le numéro tel qu’il doit apparaître pour le groupe Response Group (par exemple, +1 (425) 555-0165).

14. Module Dans **Description**, tapez la description du flux de travail que vous souhaitez voir apparaître sur la carte de visite dans le client Lync.

15. Dans **Type de flux de travail**, sélectionnez **Géré** si ce flux de travail doit être géré par un gestionnaire Response Group. Pour affecter des responsables de groupes Response Group au flux de travail, procédez comme suit :
    
    1.  Tapez l’URI SIP d’un gestionnaire pour ce flux de travail, puis cliquez sur **Ajouter**.
    
    2.  Tapez l’URI SIP des autres gestionnaires à ajouter au flux de travail, puis cliquez sur **Ajouter**.
    
    <div>
    

    > [!IMPORTANT]  
    > Tout utilisateur désigné comme responsable d’un groupe Response group doit avoir le rôle CsResponseGroupManager qui lui est assigné. Dans le cas contraire, il ne peut pas gérer de groupe Response group.

    
    </div>

16. Sous **Étape 2 Sélectionner une langue**, cliquez sur la langue à utiliser pour la reconnaissance vocale et la synthèse vocale.

17. Si vous souhaitez configurer un message de bienvenue, sous **Étape 3 Configurer un message de bienvenue**, activez la case à cocher **Lisez un message de bienvenue**, puis effectuez l’une des opérations suivantes :
    
      - Pour entrer le message de bienvenue sous forme de texte converti en message vocal pour les appelants, cliquez sur **Utiliser la synthèse vocale**, puis tapez le message de bienvenue dans la zone de texte.
        
        <div>
        

        > [!NOTE]  
        > N’incluez pas de balises HTML dans le texte que vous entrez. Sinon, vous recevrez un message d’erreur.

        
        </div>
    
      - Pour utiliser un enregistrement de fichier Wave ou Windows Media Audio pour le message de bienvenue, cliquez sur **Sélectionner un enregistrement**. Si vous souhaitez télécharger un nouveau fichier audio, cliquez sur le lien **un enregistrement**. Dans la nouvelle fenêtre de navigateur, cliquez sur **Parcourir**, sélectionnez le fichier audio que vous souhaitez utiliser, puis cliquez sur **Ouvrir**. Cliquez sur **Télécharger** pour charger le fichier audio.
        
        <div>
        

        > [!NOTE]  
        > Tous les fichiers audio fournis aux utilisateurs doivent remplir certains critères. Pour plus d’informations sur les formats de fichiers pris en charge, voir <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical Requirements for Response Group dans Lync Server 2013</A>.

        
        </div>

18. Sous **Étape 4 Spécifier vos heures d’ouverture**, dans la zone **Votre fuseau horaire**, cliquez sur le fuseau horaire du workflow.
    
    <div>
    

    > [!NOTE]  
    > Il s’agit du fuseau horaire des appelants et des agents du flux de travail. Il sert à calculer les heures d’ouverture et de fermeture. Par exemple, si le flux de travail est configuré pour utiliser le fuseau horaire Est de l’Amérique du Nord et que l’ouverture et la fermeture du flux sont planifiées respectivement pour 7 heures et 23 heures, il s’agit de l’heure d’ouverture 7:00 Est et de l’heure de fermeture 11:00:00 Est. (Vous devez entrer les heures au format 24 heures.)

    
    </div>

19. Sélectionnez le type d’heures d’ouverture que vous souhaitez utiliser en effectuant l’une des opérations suivantes :
    
      - Pour utiliser un planning prédéfini d’heures d’ouverture, cliquez sur **Utiliser un planning prédéfini**, puis sélectionnez le planning souhaité dans la liste déroulante.
        
        <div>
        

        > [!NOTE]  
        > Vous devez avoir défini précédemment au moins un planning prédéfini pour pouvoir sélectionner cette option. Vous pouvez spécifier des plannings prédéfinis à l’aide de l’applet de commande <STRONG>New-CsRgsHoursOfBusiness</STRONG>. Pour plus d’informations, reportez-vous à <A href="lync-server-2013-optional-define-response-group-business-hours.md">(facultatif) define Response Group Business hours in Lync Server 2013</A>. Lorsque vous sélectionnez un planning prédéfini, les champs <STRONG>Jour</STRONG>, <STRONG>Ouverture</STRONG> et <STRONG>Fermeture</STRONG> sont automatiquement renseignés avec les jours et les heures pendant lesquels le groupe Response Group est disponible.

        
        </div>
    
      - Pour utiliser un planning personnalisé qui s’applique uniquement à ce workflow, cliquez sur **Utiliser un planning personnalisé**.

20. Si vous créez un planning personnalisé pour ce workflow, activez les cases à cocher correspondant aux jours de la semaine pendant lesquels le groupe Response Group est disponible.

21. Si vous créez un planning personnalisé, tapez les heures **Ouverture** et **Fermeture** pendant lesquelles le groupe Response Group est disponible.
    
    <div>
    

    > [!NOTE]  
    > Les heures <STRONG>Ouverture</STRONG> et <STRONG>Fermeture</STRONG> doivent être au format 24 heures. Par exemple, si votre bureau est ouvert de 9 heures à 17 heures et ferme à midi pour le déjeuner, les heures d’ouverture sont spécifiées comme suit : <STRONG>Ouverture</STRONG> 9:00, <STRONG>Fermeture</STRONG> 12:00, <STRONG>Ouverture</STRONG> 13:00 et <STRONG>Fermeture</STRONG> 17:00.

    
    </div>

22. Si vous souhaitez que la lecture d’un message se déclenche lorsque le bureau est fermé, activez la case à cocher **Lisez un message lorsque le service Response Group est en dehors des heures d’ouverture**, puis spécifiez le message à lire en effectuant l’une des opérations suivantes :
    
      - Pour entrer le message sous forme de texte converti en message vocal pour l’appelant, cliquez sur **Utiliser la synthèse vocale**, puis tapez le message dans la zone de texte.
        
        <div>
        

        > [!NOTE]  
        > N’incluez pas de balises HTML dans le texte que vous entrez. Sinon, un message d’erreur s’affiche.

        
        </div>
    
      - Pour utiliser un enregistrement de fichier audio pour le message, cliquez sur **Sélectionner un enregistrement**. Si vous souhaitez télécharger un nouveau fichier audio, cliquez sur le lien **un enregistrement**. Dans la nouvelle fenêtre de navigateur, cliquez sur **Parcourir**, sélectionnez le fichier que vous souhaitez utiliser, puis cliquez sur **Ouvrir**. Cliquez sur **Télécharger** pour charger le fichier audio.
        
        <div>
        

        > [!NOTE]  
        > Tous les fichiers audio fournis aux utilisateurs doivent remplir certains critères. Pour plus d’informations sur les formats de fichiers pris en charge, voir <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical Requirements for Response Group dans Lync Server 2013</A>.

        
        </div>

23. Spécifiez comment gérer les appels après la lecture du message (si un message est configuré) :
    
      - Pour déconnecter l’appel, cliquez sur **Déconnecter l’appel**.
    
      - Pour transférer l’appel vers la messagerie vocale, cliquez sur **Transférer à la messagerie vocale**, puis tapez l’adresse de la messagerie vocale. Le format de l’adresse de messagerie vocale \<est\>@\<NomUtilisateur\> nom_domaine (par exemple, Bob@contoso.com).
    
      - Pour transférer l’appel vers un autre utilisateur, cliquez sur **Transférer à l’URI SIP**, puis tapez l’adresse de l’utilisateur. Le format de l’adresse de l' \<utilisateur\>@\<est\>username nom_domaine.
    
      - Pour transférer l’appel vers un autre numéro de téléphone, cliquez sur **Transférer au numéro de téléphone**, puis tapez le numéro de téléphone. Le format du numéro de téléphone est \<le\>@\<numéro\> NomDomaine (par exemple, + 14255550121@contoso.com). Le nom de domaine est utilisé pour acheminer l’appelant vers la destination appropriée.

24. Sous **Étape 5 Spécifier vos congés**, activez les cases à cocher correspondant à une ou plusieurs périodes de congés définissant les jours où le groupe Response Group est fermé.
    
    <div>
    

    > [!NOTE]  
    > Vous devez définir les congés et les périodes de congé avant de configurer le flux de travail. Utilisez les applets de commande <STRONG>New-CsRgsHoliday</STRONG> et <STRONG>New-CsRgsHolidaySet</STRONG> pour créer des congés et des périodes de congé. Pour plus d’informations, reportez-vous à <A href="lync-server-2013-optional-define-response-group-holiday-sets.md">(optional) define Response Group vacances sets in Lync Server 2013</A>.

    
    </div>

25. Si vous souhaitez que la lecture d’un message se déclenche pendant les congés, activez la case à cocher **Lisez un message pendant les congés**, puis spécifiez le message à lire en effectuant l’une des opérations suivantes :
    
      - Pour entrer le message sous forme de texte converti en message vocal pour l’appelant, cliquez sur **Utiliser la synthèse vocale**, puis tapez le message dans la zone de texte.
        
        <div>
        

        > [!NOTE]  
        > N’incluez pas de balises HTML dans le texte que vous entrez. Sinon, un message d’erreur s’affiche.

        
        </div>
    
      - Pour utiliser un enregistrement de fichier audio pour le message, cliquez sur **Sélectionner un enregistrement**. Si vous souhaitez télécharger un nouveau fichier audio, cliquez sur le lien **un enregistrement**. Dans la nouvelle fenêtre de navigateur, cliquez sur **Parcourir**, sélectionnez le fichier que vous souhaitez utiliser, puis cliquez sur **Ouvrir**. Cliquez sur **Télécharger** pour charger le fichier audio.
        
        <div>
        

        > [!NOTE]  
        > Tous les fichiers audio fournis aux utilisateurs doivent remplir certains critères. Pour plus d’informations sur les formats de fichiers audio pris en charge, voir <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical Requirements for Response Group dans Lync Server 2013</A>.

        
        </div>

26. Spécifiez comment gérer les appels après la lecture du message (si un message est configuré) :
    
      - Pour déconnecter l’appel, cliquez sur **Déconnecter l’appel**.
    
      - Pour transférer l’appel vers la messagerie vocale, cliquez sur **Transférer à la messagerie vocale**, puis tapez l’adresse de la messagerie vocale. Le format de l’adresse de messagerie vocale \<est\>@\<NomUtilisateur\> nom_domaine (par exemple, Bob@contoso.com).
    
      - Pour transférer l’appel vers un autre utilisateur, cliquez sur **Transférer à l’URI SIP**, puis tapez l’adresse de l’utilisateur. Le format de l’adresse de l' \<utilisateur\>@\<est\>username nom_domaine.
    
      - Pour transférer l’appel vers un autre numéro de téléphone, cliquez sur **Transférer au numéro de téléphone**, puis tapez le numéro de téléphone. Le format du numéro de téléphone est \<le\>@\<numéro\> NomDomaine (par exemple, + 14255550121@contoso.com). Le nom de domaine est utilisé pour acheminer l’appelant vers la destination appropriée.

27. Sous **Étape 6 Configurer une attente musicale**, choisissez ce que les appelants entendront pendant l’attente d’un agent. Pour cela, procédez de l’une des façons suivantes :
    
      - Pour utiliser l’enregistrement d’attente musicale par défaut, cliquez sur **Utiliser la valeur par défaut**.
    
      - Pour utiliser un enregistrement de fichier audio pour l’attente musicale, cliquez sur **Sélectionner un fichier de musique**. Si vous souhaitez télécharger un nouveau fichier audio, cliquez sur le lien **un fichier de musique**. Dans la nouvelle fenêtre de navigateur, cliquez sur **Parcourir**, sélectionnez le fichier que vous souhaitez utiliser, puis cliquez sur **Ouvrir**. Cliquez sur **Télécharger** pour charger le fichier audio.
        
        <div>
        

        > [!NOTE]  
        > Tous les fichiers audio fournis aux utilisateurs doivent remplir certains critères. Pour plus d’informations sur les formats de fichiers pris en charge, voir <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical Requirements for Response Group dans Lync Server 2013</A>.

        
        </div>

28. Sous **Étape 7 Configurer la réponse vocale interactive**, dans l’en-tête **L’utilisateur entendra le texte ou message enregistré suivant**, spécifiez comme suit la question à poser aux appelants :
    
      - Pour entrer la question au format texte, cliquez sur **Utiliser la synthèse vocale**, puis tapez la question dans la zone de texte.
        
        <div>
        

        > [!NOTE]  
        > N’incluez pas de balises HTML dans le texte que vous entrez. Si vous incluez des balises HTML, vous recevrez un message d’erreur.

        
        </div>
        
        <div>
        

        > [!NOTE]  
        > Le moteur de synthèse vocale traduit le symbole « # » par le mot « numéro ». Pour faire référence à la touche #, utilisez le nom de celle-ci au lieu de son symbole dans votre message d’invite. Par exemple, « Pour être mis en relation avec le service commercial, appuyez sur la touche dièse ».

        
        </div>
    
      - Pour utiliser un fichier audio préenregistré contenant la question, cliquez sur **Sélectionner un enregistrement**, puis cliquez sur le lien **un enregistrement** pour télécharger le fichier. Dans la nouvelle fenêtre de navigateur, cliquez sur **Parcourir**, sélectionnez le fichier audio, puis cliquez sur **Ouvrir**. Cliquez sur **Télécharger** pour charger le fichier, puis tapez éventuellement la question dans la zone de texte (la question, ainsi que la réponse de l’appelant seront transférées à l’agent qui répond).
        
        <div>
        

        > [!NOTE]  
        > Tous les fichiers audio fournis aux utilisateurs doivent remplir certains critères. Pour plus d’informations sur les formats de fichiers pris en charge, voir <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical Requirements for Response Group dans Lync Server 2013</A>.

        
        </div>

29. Sous **Réponse 1**, procédez comme suit pour spécifier la première réponse possible à la question :
    
    <div>
    

    > [!IMPORTANT]  
    > N’incluez pas de guillemets (") dans les réponses vocales. Les guillemets entraînent l’échec de la réponse vocale interactive (IVR).

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Vous pouvez choisir d’autoriser les appelants à répondre via une réponse vocale et/ou le clavier alphanumérique.

    
    </div>
    
      - Si vous souhaitez permettre à l’appelant de répondre à l’aide d’une réponse vocale, entrez la réponse dans **Entrer une réponse vocale**.
    
      - Si vous souhaitez permettre à l’appelant de répondre en appuyant sur une touche du pavé numérique, dans **Chiffre**, cliquez sur le chiffre du pavé numérique.

30. Spécifiez si l’appelant doit être acheminé vers une file d’attente ou si une autre question doit être posée. Pour ce faire, procédez comme suit :
    
      - Pour acheminer l’appelant vers une file d’attente, cliquez sur **Envoyer vers une file d’attente** et, dans **Sélectionner une file d’attente**, cliquez sur la file d’attente que vous souhaitez utiliser.
    
      - Pour poser une autre question, cliquez sur **Poser une autre question**, puis cliquez sur **Utiliser la synthèse vocale** et tapez la question, ou cliquez sur **Sélectionner un enregistrement**. Utilisez les regroupements de réponses de cette section pour spécifier jusqu’à quatre réponses possibles à la question supplémentaire, ainsi que la file d’attente à utiliser pour chaque réponse. Pour spécifier une troisième ou quatrième réponse possible, cochez la case **Réponse 3** ou **Réponse 4**.

31. Spécifiez jusqu’à trois autres réponses possibles à la question d’origine en répétant les étapes 28 et 29, pour indiquer les réponses possibles et l’action à effectuer pour chaque réponse. Pour spécifier une troisième ou quatrième réponse possible, cochez la case **Réponse 3** ou **Réponse 4**.

32. Cliquez sur **Déployer**.

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-an-interactive-workflow"></a>Pour utiliser Windows PowerShell pour créer ou modifier un flux de travail interactif

1.  Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre d’un des rôles d’administration prédéfinis prenant en charge Response Group.

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

3.  Déterminez le nom du service Response Group et affectez-le à une variable. À partir de la ligne de commande, exécutez la commande suivante :
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -like "*RGS*"}).ServiceId;

4.  Un flux de travail interactif nécessite au moins deux files d’attente et plusieurs groupes d’agents. Créez tout d’abord les groupes d’agents. Exécutez le code suivant :
    
        $AGSupport = New-CsRgsAgentGroup -Parent $serviceId -Name "Technical Support" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:agent1@contoso.com", "sip:agent2@contoso.com")]
        $AGSales = New-CsRgsAgentGroup -Parent $serviceId -Name "Sales Team" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:bob@contoso.com", "sip:alice@contoso.com")]

5.  Créez des files d’attente. Exécutez :
    
        $QSupport = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Support" -AgentGroupIDList($AG-Support.Identity)
        $QSales = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Sales" -AgentGroupIDList($AG-Sales.Identity)

6.  Créez la première invite Response group. Exécutez le code suivant :
    
        $SupportPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please be patient while we connect you with Contoso Technical Support."

7.  Créez ensuite l’action à effectuer après l’invite. Exécutez le code suivant :
    
        $SupportAction = New-CsRgsCallAction -Prompt $SupportPrompt -Action TransferToQueue -QueueID $QSupport.Identity

8.  Créez la première réponse Response group. Exécutez le code suivant :
    
        $SupportAnswer = New-CsRgsAnswer -Action $SupportAction [-DtmfResponse 1]

9.  Créez maintenant les deuxièmes invite, action d’appel et réponse. Créez d’abord l’invite. Exécutez le code suivant :
    
        $SalesPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please hold while we connect you with Contoso Sales."

10. Créez la deuxième action d’appel. Exécutez le code suivant :
    
        $SalesAction = New-CsRgsCallAction -Prompt $SalesPrompt -Action TransferToQueue -QueueID $QSales.Identity

11. Créez la seconde réponse Response group. Exécutez le code suivant :
    
        $SalesAnswer = New-CsRgsAnswer -Action $SalesAction [-DtmfResponse 2]

12. Créez l’invite de niveau supérieur. Exécutez :
    
        $TopLevelPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Thank you for calling Contoso. For Technical Support, press 1. For a Sales Representative, press 2."

13. Créez la question de niveau supérieur. Exécutez :
    
        $TopLevelQuestion = New-CsRgsQuestion -Prompt $TopLevelPrompt [-AnswerList ($SupportAnswer, $SalesAnswer)]

14. Créez maintenant le flux de travail. Exécutez :
    
        $IVRAction = New-CsRgsCallAction -Action TransferToQuestion [-Question $Question]
        $IVRWorkflow = New-CsRgsWorkflow -Parent $ServiceId -Name "Contoso Helpdesk" [-Description "The Contoso Helpdesk line."] -PrimaryUri "sip:helpdesk@contoso.com" [-LineUri tel:+14255554321] [-DisplayNumber "+1 (425) 555-4321"] [-Active $true] [-Anonymous $true] [-DefaultAction $IVRAction] [-Managed $true] [-ManagersByURI ("sip:mindy@contoso.com", "sip:bob@contoso.com")]
    
    <div>
    

    > [!NOTE]  
    > Tous les utilisateurs désignés comme responsables d’un groupe Response group doivent avoir le rôle CsResponseGroupManager qui leur est assigné. Dans le cas contraire, ils ne peuvent pas gérer de groupe Response group.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

