---
title: 'Lync Server 2013 : création ou modification d’un flux de travail de groupe de recherche'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a hunt group workflow
ms:assetid: dcb9effb-5d12-4dee-80fc-ab9654222d5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205321(v=OCS.15)
ms:contentKeyID: 48185596
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e56a93ae0be1fd6f047dc6cde724afbea7aa4064
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758058"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-hunt-group-workflow-in-lync-server-2013"></a>Création ou modification d’un flux de travail de groupe de recherche dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-09-11_

Pour créer ou modifier un flux de travail de groupe de recherche, utilisez l’une des procédures suivantes.

<div>


> [!NOTE]  
> Vous pouvez utiliser Lync Server Management Shell ou l’outil de configuration de Response Group pour créer et modifier des flux de travail de groupe de recherche. Vous pouvez accéder à l’outil de configuration de Response Group à partir du panneau de configuration de Lync Server ou en ouvrant la page Web directement à partir d’un navigateur Web en tapant l’URL suivante : <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.



</div>

<div>

## <a name="to-use-response-group-configuration-tool-to-create-or-modify-a-hunt-group-workflow"></a>Pour utiliser l’outil de configuration de groupe de réponse pour créer ou modifier un flux de travail de groupe de recherche

1.  Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre de l’un des rôles d’administration prédéfinis prenant en charge Response Group.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Services Response Group**, puis sur **Flux de travail**.

4.  Dans la page **Flux de travail**, cliquez sur **Créer ou modifier un flux de travail**.

5.  Dans le champ de recherche **Sélectionner un service**, tapez entièrement ou partiellement le nom du service **ApplicationServer** qui héberge le flux de travail à créer ou à modifier. Dans la liste des services obtenus, cliquez sur le service de votre choix, puis sur **OK**.
    
    <div>
    

    > [!NOTE]  
    > L’outil de configuration de Response Group s’ouvre. Vous pouvez également ouvrir l’outil de configuration de groupe de réponse directement à partir d’un navigateur Web en tapant l’URL suivante : <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.

    
    </div>

6.  Effectuez l’une des actions suivantes :
    
      - Sous **Créer un flux de travail**, en regard de **Groupe de recherche, cliquez sur Créer**.
    
      - Sous **Gérer un flux de travail existant**, recherchez le flux de travail à modifier, puis sous **Action**, cliquez sur **Modifier**.

7.  Si vous êtes prêt et que les utilisateurs peuvent commencer à appeler le flux de travail, activez la case à cocher **Activer le flux de travail**.
    
    <div>
    

    > [!NOTE]  
    > Si vous créez un flux de travail géré, vous devez sélectionner <STRONG>Activer le flux de travail</STRONG>. Une fois que vous avez enregistré le flux de travail géré actif, vous pouvez le modifier et le désactiver.

    
    </div>

8.  Pour autoriser les utilisateurs fédérés à appeler le groupe, activez la case à cocher **Activer pour la fédération**. Vous devez également disposer d’une stratégie d’accès externe qui s’applique à l’application de Response Group configurée pour la Fédération.
    
    <div>
    

    > [!NOTE]  
    > La stratégie d’accès externe globale s’applique à l’application Response Group. Vous pouvez configurer la stratégie globale pour la Fédération de groupe de réponse en utilisant le panneau de configuration de Lync Server ou en utilisant l’applet de commande <STRONG>Set-CsExternalAccessPolicy</STRONG> pour définir le paramètre EnableOutsideAccess sur true. Gardez à l’esprit que les paramètres de stratégie globale s’appliquent à tous les utilisateurs sauf s’ils sont affectés à un site ou une stratégie d’utilisateur. Par conséquent, avant de modifier ce paramètre pour les groupes Response Group, assurez-vous que le paramètre de fédération satisfait les exigences de votre organisation. Pour plus d’informations sur l’application des stratégies aux utilisateurs, voir <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">gérer une stratégie d’accès externe dans Lync Server 2013</A>. Pour plus d’informations sur le paramètre de Fédération, voir <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy">Set-CsExternalAccessPolicy</A>.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Les utilisateurs hébergés sur Lync Online ne peuvent pas passer d’appels vers des groupes de réponse hébergés dans un déploiement local. C’est vrai dans les déploiements hybrides et dans les cas où un déploiement local est fédéré avec un déploiement Lync Online.

    
    </div>

9.  Pour masquer l’identité des agents pendant les appels, activez la case à cocher **Activer l’anonymat de l’agent**.
    
    <div>
    

    > [!NOTE]  
    > Les appels anonymes ne peuvent pas commencer par la messagerie instantanée ou la vidéo, mais l’agent ou l’appelant peut ajouter la messagerie instantanée et la vidéo une fois que l’appel a commencé. Un agent anonyme peut également mettre des appels en attente, transférer des appels (transferts invisibles et consultatifs), mais aussi parquer et récupérer des appels. Les appels anonymes ne prennent pas en charge la conférence, le partage d’application, le partage du Bureau, le transfert de fichiers, le tableau blanc, la collaboration de données et l’enregistrement d’appel. Les agents utilisant le plugin Lync VDI peuvent recevoir des appels entrants anonymes, mais ils ne peuvent pas effectuer d’appels sortants anonymes.

    
    </div>

10. Sous **Entrez l’adresse du groupe qui recevra les appels**, cliquez sur l’adresse URI SIP (Session Initiation Protocol) principale du groupe qui doit prendre les appels vers le flux de travail.
    
    <div>
    

    > [!NOTE]  
    > L’URI principal pour un flux de travail définit les modalités d’identification et de référencement du flux de travail. L’URI SIP que vous entrez est créé en tant qu’objet de contact dans les services de domaine Active Directory (AD FS). Pour créer l’URI, l’objet doit être unique dans Active Directory.

    
    </div>

11. Dans **nom complet**, tapez le nom que vous voulez afficher pour le flux de travail (par exemple, groupe réponse vente).
    
    <div>
    

    > [!NOTE]  
    > N’incluez pas les&lt;caractères « »&gt;ou « » dans le nom d’affichage. N’utilisez pas les noms d’affichage ci-dessous, car ils sont réservés : <STRONG>RGS Presence Watcher</STRONG> ou <STRONG>Service d’annonce</STRONG>.

    
    </div>

12. Sous **Numéro de téléphone**, tapez l’URI de ligne pour le groupe Response Group (par exemple, +14255550165).

13. Dans **Numéro affiché**, tapez le numéro tel qu’il doit s’afficher pour le groupe Response Group (par exemple, +1 (425) 555-0165).

14. Facultatif Dans **Description**, tapez une description pour le flux de travail tel que vous voulez qu’il apparaisse sur la carte de visite dans le client Lync.

15. Dans **Type de flux de travail**, sélectionnez **Géré** si ce flux de travail sera géré par un responsable de groupes Response Group. Pour affecter des responsables de groupe de réponse au flux de travail, procédez comme suit :
    
    1.  Tapez l’URI SIP (Session Initiation Protocol) d’un responsable pour ce flux de travail, puis cliquez sur **Ajouter**.
    
    2.  Tapez l’URI SIP (Session Initiation Protocol) d’autres responsables à ajouter au flux de travail, puis cliquez sur **Ajouter**.
    
    <div>
    

    > [!IMPORTANT]  
    > Tous les utilisateurs désignés comme responsables d’un groupe Response Group doivent posséder le rôle CsResponseGroupManager. Si les utilisateurs n’ont pas ce rôle, ils ne peuvent pas gérer les groupes Response Group.

    
    </div>

16. Dans **Étape 2 Sélection d’une langue**, cliquez sur la langue à utiliser pour la reconnaissance vocale et la conversion de texte par synthèse vocale.

17. Si vous souhaitez configurer un message de bienvenue, dans **Étape 3 Configuration d’un message de bienvenue**, activez la case à cocher **Lisez un message de bienvenue**, puis effectuez l’une des opérations suivantes :
    
      - Pour entrer le message de bienvenue sous forme de texte converti en message vocal pour les appelants, cliquez sur **Utiliser la synthèse vocale**, puis tapez le message de bienvenue dans la zone de texte.
        
        <div>
        

        > [!NOTE]  
        > N’incluez pas de balises HTML dans le texte que vous entrez. Si vous incluez des balises HTML, vous recevrez un message d’erreur.

        
        </div>
    
      - Pour utiliser un enregistrement de fichier son (.wav) ou audio Windows Media (.wma) pour le message de bienvenue, cliquez sur **Sélectionner un enregistrement**. Si vous souhaitez télécharger un nouveau fichier audio, cliquez sur le lien **un enregistrement**. Dans la nouvelle fenêtre de navigateur, cliquez sur **Parcourir**, sélectionnez le fichier audio à utiliser, puis cliquez sur **Ouvrir**. Cliquez sur **Télécharger** pour charger le fichier audio.
        
        <div>
        

        > [!NOTE]  
        > Tous les fichiers audio fournis aux utilisateurs doivent remplir certains critères. Pour plus d’informations sur les formats de fichiers pris en charge, voir <A href="lync-server-2013-technical-requirements-for-response-group.md">configuration technique requise pour Response Group dans Lync Server 2013</A>.

        
        </div>

18. Dans **Étape 4 Spécification de vos heures d’ouverture**, dans la zone **Votre fuseau horaire**, sélectionnez le fuseau horaire du flux de travail.
    
    <div>
    

    > [!NOTE]  
    > Il s’agit du fuseau horaire des appelants et des agents du flux de travail. Il est utilisé pour calculer les heures d’ouverture et de fermeture. Par exemple, si le flux de travail est configuré pour utiliser le fuseau horaire Est de l’Amérique du Nord et que l’ouverture et la fermeture du flux de travail sont planifiées respectivement pour 7 heures et 23 heures, il s’agit de l’heure d’ouverture 7:00 Est et de l’heure de fermeture 23:00 Est. (Vous devez entrer les heures au format 24 heures.)

    
    </div>

19. Sélectionnez le type d’heures d’ouverture à utiliser en effectuant l’une des opérations suivantes :
    
      - Pour utiliser un planning prédéfini d’heures d’ouverture, cliquez sur **Utiliser un planning prédéfini**, puis sélectionnez le planning souhaité dans la liste déroulante.
        
        <div>
        

        > [!NOTE]  
        > Pour sélectionner cette option, vous devez avoir défini précédemment au moins un planning prédéfini. Vous pouvez spécifier des plannings prédéfinis à l’aide de l’applet de commande <STRONG>New-CSRgsHoursOfBusiness</STRONG>. Pour plus d’informations, reportez-vous à la section <A href="lync-server-2013-optional-define-response-group-business-hours.md">définir les heures d’activité du groupe de réponses dans Lync Server 2013</A>.

        
        </div>
        
        <div>
        

        > [!NOTE]  
        > Lorsque vous sélectionnez un planning prédéfini, les champs <STRONG>Jour</STRONG>, <STRONG>Ouverture</STRONG> et <STRONG>Fermeture</STRONG> sont renseignés automatiquement avec les jours et les heures de disponibilité du groupe Response Group.

        
        </div>
    
      - Pour utiliser un planning personnalisé qui ne s’applique qu’à ce flux de travail, cliquez sur **Utiliser un planning personnalisé**.

20. Si vous créez un planning personnalisé pour ce flux de travail, activez les cases à cocher correspondant aux jours de la semaine pendant lesquels le groupe Response Group est disponible.

21. Si vous créez un planning personnalisé, tapez les heures d’**ouverture** et de **fermeture** pour chaque jour de la semaine pendant lesquelles le groupe Response Group est disponible.
    
    <div>
    

    > [!NOTE]  
    > Les heures <STRONG>Ouverture</STRONG> et <STRONG>Fermeture</STRONG> doivent être au format 24 heures. Par exemple, si votre bureau est ouvert de 9 heures à 17 heures et fermé à midi pour le déjeuner, les heures d’ouverture sont spécifiées comme suit : <STRONG>Ouverture</STRONG> 9:00, <STRONG>Fermeture</STRONG> 12:00, <STRONG>Ouverture</STRONG> 13:00 et <STRONG>Fermeture</STRONG> 17:00.

    
    </div>

22. Si vous souhaitez que la lecture d’un message se déclenche lorsque le bureau est fermé, activez la case à cocher **Lisez un message lorsque le service Response Group est en dehors des heures d’ouverture**, puis spécifiez le message à lire en effectuant l’une des opérations suivantes :
    
      - Pour entrer le message sous forme de texte converti en message vocal pour l’appelant, cliquez sur **Utiliser la synthèse vocale**, puis tapez le message dans la zone de texte.
        
        <div>
        

        > [!NOTE]  
        > N’incluez pas de balises HTML dans le texte que vous entrez. Si vous incluez des balises HTML, vous recevrez un message d’erreur.

        
        </div>
    
      - Pour utiliser un enregistrement de fichier audio pour le message, cliquez sur **Sélectionner un enregistrement**. Si vous souhaitez télécharger un nouveau fichier audio, cliquez sur le lien **un enregistrement**. Dans la nouvelle fenêtre de navigateur, cliquez sur **Parcourir**, sélectionnez le fichier à utiliser, puis cliquez sur **Ouvrir**. Cliquez sur **Télécharger** pour charger le fichier audio.
        
        <div>
        

        > [!NOTE]  
        > Tous les fichiers audio fournis aux utilisateurs doivent remplir certains critères. Pour plus d’informations sur les formats de fichiers audio pris en charge, voir <A href="lync-server-2013-technical-requirements-for-response-group.md">configuration technique requise pour Response Group dans Lync Server 2013</A>.

        
        </div>

23. Spécifiez comment gérer les appels après la lecture du message (si un message est configuré) :
    
      - Pour déconnecter l’appel, cliquez sur **Déconnecter l’appel**.
    
      - Pour transférer l’appel vers la messagerie vocale, cliquez sur **Transférer à la messagerie vocale**, puis tapez l’adresse de la messagerie vocale. Le format de l’adresse de messagerie vocale \<est\>@\<nom\> d’utilisateur nom_domaine (par exemple, Bob@contoso.com).
    
      - Pour transférer l’appel vers un autre utilisateur, cliquez sur **Transférer à l’URI SIP**, puis tapez l’adresse de l’utilisateur. Le format de l’adresse utilisateur est \<nom\>@\<d'\>utilisateur nom_domaine.
    
      - Pour transférer l’appel vers un autre numéro de téléphone, cliquez sur **Transférer au numéro de téléphone**, puis tapez le numéro de téléphone. Le format de numéro de téléphone est \<le\>@\<numéro\> nom_domaine (par exemple, + 14255550121@contoso.com). Le nom de domaine est utilisé pour router l’appelant vers la destination appropriée.

24. Dans **Étape 5 Spécification de vos congés**, activez les cases à cocher correspondant à une ou plusieurs périodes de congés définissant les jours de fermeture du groupe Response Group.
    
    <div>
    

    > [!NOTE]  
    > Vous devez définir les congés et les périodes de congé avant de configurer le flux de travail. Utilisez les applets de commande <STRONG>New-CsRgsHoliday</STRONG> et <STRONG>New-CsRgsHolidaySet</STRONG> pour créer des congés et des périodes de congé. Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-optional-define-response-group-holiday-sets.md">définir (facultatif) des jeux de vacances de groupe de réponses dans Lync Server 2013</A>.

    
    </div>

25. Si vous souhaitez que la lecture d’un message se déclenche pendant les congés, activez la case à cocher **Lisez un message pendant les congés**, puis spécifiez le message à lire en effectuant l’une des opérations suivantes :
    
      - Pour entrer le message sous forme de texte converti en message vocal pour l’appelant, cliquez sur **Utiliser la synthèse vocale**, puis tapez le message dans la zone de texte.
        
        <div>
        

        > [!NOTE]  
        > N’incluez pas de balises HTML dans le texte que vous entrez. Si vous incluez des balises HTML, vous recevrez un message d’erreur.

        
        </div>
    
      - Pour utiliser un enregistrement de fichier audio pour le message, cliquez sur **Sélectionner un enregistrement**. Si vous souhaitez télécharger un nouveau fichier audio, cliquez sur le lien **un enregistrement**. Dans la nouvelle fenêtre de navigateur, cliquez sur **Parcourir**, sélectionnez le fichier à utiliser, puis cliquez sur **Ouvrir**. Cliquez sur **Télécharger** pour charger le fichier audio.
        
        <div>
        

        > [!NOTE]  
        > Tous les fichiers audio fournis aux utilisateurs doivent remplir certains critères. Pour plus d’informations sur les formats de fichiers audio pris en charge, voir <A href="lync-server-2013-technical-requirements-for-response-group.md">configuration technique requise pour Response Group dans Lync Server 2013</A>.

        
        </div>

26. Spécifiez comment gérer les appels après la lecture du message (si un message est configuré) :
    
      - Pour déconnecter l’appel, cliquez sur **Déconnecter l’appel**.
    
      - Pour transférer l’appel vers la messagerie vocale, cliquez sur **Transférer à la messagerie vocale**, puis tapez l’adresse de la messagerie vocale. Le format de l’adresse de messagerie vocale \<est\>@\<nom\> d’utilisateur nom_domaine (par exemple, Bob@contoso.com).
    
      - Pour transférer l’appel vers un autre utilisateur, cliquez sur **Transférer à l’URI SIP**, puis tapez l’adresse de l’utilisateur. Le format de l’adresse utilisateur est \<nom\>@\<d'\>utilisateur nom_domaine.
    
      - Pour transférer l’appel vers un autre numéro de téléphone, cliquez sur **Transférer au numéro de téléphone**, puis tapez le numéro de téléphone. Le format de numéro de téléphone est \<le\>@\<numéro\> nom_domaine (par exemple, + 14255550121@contoso.com). Le nom de domaine est utilisé pour router l’appelant vers la destination appropriée.

27. Dans **Étape 6 Configuration d’une file d’attente**, dans **Sélectionnez la file d’attente qui reçoit les appels**, sélectionnez la file d’attente dans laquelle mettre les appelants en attendant qu’un agent soit disponible.

28. Dans **Étape 7 Configuration d’une attente musicale**, choisissez la musique que les appelants entendront pendant qu’ils attendent un agent. Pour cela, procédez de l’une des façons suivantes :
    
      - Pour utiliser l’enregistrement d’attente musicale par défaut, cliquez sur **Utiliser la valeur par défaut**.
    
      - Pour utiliser un enregistrement de fichier audio pour l’attente musicale, cliquez sur **Sélectionner un fichier de musique**. Si vous souhaitez télécharger un nouveau fichier audio, cliquez sur le lien **un fichier de musique**. Dans la nouvelle fenêtre de navigateur, cliquez sur **Parcourir**, sélectionnez le fichier à utiliser, puis cliquez sur **Ouvrir**. Cliquez sur **Télécharger** pour charger le fichier audio.
        
        <div>
        

        > [!NOTE]  
        > Tous les fichiers audio fournis aux utilisateurs doivent remplir certains critères. Pour plus d’informations sur les formats de fichiers audio pris en charge, voir <A href="lync-server-2013-technical-requirements-for-response-group.md">configuration technique requise pour Response Group dans Lync Server 2013</A>.

        
        </div>

29. Cliquez sur **Déployer**.

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-a-hunt-group-workflow"></a>Pour utiliser Windows PowerShell afin de créer ou de modifier un flux de travail de groupe de recherche

1.  Ouvrez une session en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre de l’un des rôles d’administration prédéfinis prenant en charge Response Group.

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Créez l’invite à exécuter pour le message de bienvenue, et enregistrez-la dans une variable. Dans la ligne de commande, exécutez la commande suivante :
    
        $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    Par exemple :
    
        $promptWM = New-CsRgsPrompt -TextToSpeechPrompt "Welcome to Contoso. Please wait for an available agent."
    
    <div>
    

    > [!NOTE]  
    > Pour utiliser un fichier audio pour l’invite, utilisez l’applet de commande <STRONG>Import-CsRgsAudioFile</STRONG>. Pour plus d’informations, voir <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.

    
    </div>

4.  Obtenez l’identité de la file d’attente ou demandez où les appels seront dirigés. Dans la ligne de commande, exécutez la commande suivante :
    
        $qid = (Get-CsRgsQueue -Name "Help Desk").Identity
    
    Pour plus d’informations sur la création de la file d’attente, voir [New-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/New-CsRgsQueue).

5.  Définissez l’action par défaut à effectuer lorsqu’un flux de travail est ouvert pendant les heures ouvrées et enregistrez-la dans une variable. Dans la ligne de commande, exécutez la commande suivante :
    
        $actionWM = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken> -QueueID $qid
    
    <div>
    

    > [!NOTE]  
    > Pour les flux de travail de groupe de recherche, l’action par défaut doit rediriger l’appel vers une file d’attente. Ce paramètre est obligatoire pour les flux de travail actifs. Il ne l’est pas pour les flux de travail inactifs.

    
    </div>
    
    Exemple :
    
        $actionWM = New-CsRgsCallAction -Prompt $promptWM -Action TransferToQueue -QueueID $qid.Identity

6.  Si vous voulez définir des heures ouvrées et des congés, vous devez les créer avant de créer et modifier le flux de travail. Pour plus d’informations, reportez-vous à la section [définir les heures d’activité du groupe de réponses dans Lync server 2013](lync-server-2013-optional-define-response-group-business-hours.md) et [(facultatif) définir les jeux de vacances du groupe réponse dans Lync Server 2013](lync-server-2013-optional-define-response-group-holiday-sets.md).

7.  Pour avoir des invites pour les appels reçus en dehors des heures ouvrées ou pendant des congés, utilisez l’applet de commande **New-CsRgsPrompt** pour définir l’invite et **New-CsRgsCallAction** pour définir l’action à effectuer après l’invite. Pour plus d’informations, reportez-vous à [New-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt) et [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction).

8.  Récupérez le nom du service pour le service du groupe de réponses du serveur Lync et attribuez-le à une variable. Dans la ligne de commande, exécutez la commande suivante :
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -like "*RGS*"}).ServiceId;

9.  Créez ou modifiez le flux de travail. Pour créer un flux de travail, utilisez **New-CsRgsWorkflow**. Pour modifier un flux de travail, utilisez **Set-CsRgsWorkflow**. Dans la ligne de commande, tapez :
    
        $workflowHG = New-CsRgsWorkflow -Parent <service ID for the Response Group service> -Name "<hunt group name>" [-Description "<hunt group description>"] -PrimaryUri "<SIP address for the workflow>" [-LineUri "<Phone number for the workflow>"] [-DisplayNumber "<Phone number displayed in Lync>"] [-Active <$true | $false>] [-Anonymous <$true | $false>] [-DefaultAction <variable from preceding step>] [-EnabledForFederation <$true | $false>] [-Managed <$true | $false>] [-MangersByUri <SIP addresses for Response Group Managers who can manage the workflow>]
    
    Par exemple :
    
        $workflowHG = New-CsRgsWorkflow -Parent $serviceID -Name "Human Resources" -Description "Human Resources workflow" -PrimaryUri "sip:humanresources@contoso.com" -LineUri "TEL:+14255551219" -DisplayNumber "555-1219" -Active $true -Anonymous $true -DefaultAction $actionWM -EnabledForFederation $false -Managed $true -ManagersByUri "sip:bob@contoso.com", "mindy@contoso.com"
    
    <div>
    

    > [!IMPORTANT]  
    > Tous les utilisateurs désignés comme responsables pour les flux de travail doivent posséder le rôle CsResponseGroupManager.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Pour plus d’informations sur les paramètres facultatifs supplémentaires, voir <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsWorkflow">New-CsRgsWorkflow</A> ou <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsRgsWorkflow">Set-CsRgsWorkflow</A>

    
    </div>

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Facultatif Définir des jeux de vacances de groupe de réponse dans Lync Server 2013](lync-server-2013-optional-define-response-group-holiday-sets.md)  


[Facultatif Définir les heures d’activité du groupe de réponses dans Lync Server 2013](lync-server-2013-optional-define-response-group-business-hours.md)  


[Nouveau-CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/New-CsRgsWorkflow)  
[Set-CsRgsWorkflow](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsWorkflow)  
[New-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt)  
[Nouveau-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

