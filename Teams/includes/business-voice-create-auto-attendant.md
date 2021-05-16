#### <a name="video-demonstration"></a><span data-ttu-id="e68d5-101">Démonstration vidéo</span><span class="sxs-lookup"><span data-stu-id="e68d5-101">Video demonstration</span></span>

<span data-ttu-id="e68d5-102">Cette vidéo montre un exemple de base de la création d’un attendant automatique dans Teams.</span><span class="sxs-lookup"><span data-stu-id="e68d5-102">This video shows a basic example of how to create an auto attendant in Teams.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWEnCG?autoplay=false]

#### <a name="before-you-begin"></a><span data-ttu-id="e68d5-103">Avant de commencer</span><span class="sxs-lookup"><span data-stu-id="e68d5-103">Before you begin</span></span>

<span data-ttu-id="e68d5-104">Obtenez les numéros de service (les numéros de service sont un type spécial de numéro de téléphone utilisé par les agents automatiques) dont vous avez besoin pour les numéros de service automatiques que vous souhaitez rendre accessibles en composant un numéro direct depuis l’extérieur de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="e68d5-104">Get the service numbers (service numbers are a special type of phone number that are used by auto attendants) that you need for the auto attendants that you want to be accessible by direct dialing from outside your organization.</span></span> <span data-ttu-id="e68d5-105">Cela peut inclure [le transfert de numéros d’un autre fournisseur](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md) ou la demande de nouveaux numéros de [service.](../getting-service-phone-numbers.md)</span><span class="sxs-lookup"><span data-stu-id="e68d5-105">This might include [transferring numbers from another provider](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md) or [requesting new service numbers](../getting-service-phone-numbers.md).</span></span>

<span data-ttu-id="e68d5-106">Un utilisateur virtuel doit être affecté à Système téléphonique attendant automatique.</span><span class="sxs-lookup"><span data-stu-id="e68d5-106">Each auto attendant needs to be assigned a Phone System - Virtual User license.</span></span> <span data-ttu-id="e68d5-107">Lorsque vous avez acheté Business Voice, vous recevez également un certain nombre de Système téléphonique - Licences utilisateur virtuels. Vous n’avez donc probablement pas besoin d’en demander davantage.</span><span class="sxs-lookup"><span data-stu-id="e68d5-107">When you purchased Business Voice, you also received a number of Phone System - Virtual User licenses, so you probably don't need to request more.</span></span> <span data-ttu-id="e68d5-108">Toutefois, si vous en avez besoin à l’avenir, vous pouvez les obtenir en suivant les instructions de Système téléphonique - Licence utilisateur [virtuel.](../teams-add-on-licensing/virtual-user.md)</span><span class="sxs-lookup"><span data-stu-id="e68d5-108">However, if you need more in the future, you can get them by following the instructions in [Phone System - Virtual User license](../teams-add-on-licensing/virtual-user.md).</span></span>

<span data-ttu-id="e68d5-109">Si vous souhaitez utiliser un itinéraire des appels [](../set-up-holidays-in-teams.md) différent pour les jours fériés, créez les jours fériés que vous voulez utiliser avant de créer le attendant automatique.</span><span class="sxs-lookup"><span data-stu-id="e68d5-109">If you want to have your auto attendant route calls differently on holidays, then [create the holidays that you want to use](../set-up-holidays-in-teams.md) before you create the auto attendant.</span></span>

<a name="steps"></a>

#### <a name="follow-these-steps-to-set-up-your-auto-attendant"></a><span data-ttu-id="e68d5-110">Pour configurer votre attendant automatique, suivez les étapes ci-après</span><span class="sxs-lookup"><span data-stu-id="e68d5-110">Follow these steps to set up your auto attendant</span></span>

# <a name="step-1brphone-number"></a>[<span data-ttu-id="e68d5-111">Numéro de Téléphone <br> étape 1</span><span class="sxs-lookup"><span data-stu-id="e68d5-111">Step 1<br>Phone number</span></span>](#tab/phone-number)

> [!NOTE]
> <span data-ttu-id="e68d5-112">Si vous devez configurer Voix Entreprise pour la première fois et que vous en êtes à l’étape **6**: configurer un attendant automatique pour le numéro de téléphone principal de votre entreprise, vous avez déjà terminé les étapes de cet onglet. Passer à l’onglet suivant : informations générales [sur le attendant automatique.](?tabs=general-info#steps)</span><span class="sxs-lookup"><span data-stu-id="e68d5-112">If you're following the steps to set up Business Voice for the first time and you're on **Step 6: Set up an auto attendant for your company's main phone number**, you've already finished the steps on this tab. Move to the next tab: [Auto attendant general info](?tabs=general-info#steps).</span></span>

<span data-ttu-id="e68d5-113">Chaque employé automatique que vous créez nécessite un compte de ressource.</span><span class="sxs-lookup"><span data-stu-id="e68d5-113">Each auto attendant that you create requires a resource account.</span></span> <span data-ttu-id="e68d5-114">Ce compte est similaire à un compte d’utilisateur, sauf qu’il est associé à un service de attendant automatique ou à une file d’attente d’appels au lieu d’une personne.</span><span class="sxs-lookup"><span data-stu-id="e68d5-114">This is similar to a user account, except the account is associated with an auto attendant or call queue instead of a person.</span></span> <span data-ttu-id="e68d5-115">Dans cette étape, nous allons créer le compte, lui attribuer *une Microsoft 365 Système téléphonique -licence* Utilisateur virtuel, puis attribuer un numéro de service.</span><span class="sxs-lookup"><span data-stu-id="e68d5-115">In this step, we'll create the account, assign it a *Microsoft 365 Phone System - Virtual User* license, and then assign a service number.</span></span>

### <a name="create-a-resource-account"></a><span data-ttu-id="e68d5-116">Créer un compte de ressource</span><span class="sxs-lookup"><span data-stu-id="e68d5-116">Create a resource account</span></span>

<span data-ttu-id="e68d5-117">Vous pouvez créer un compte de ressource dans le Teams d’administration.</span><span class="sxs-lookup"><span data-stu-id="e68d5-117">You can create a resource account in the Teams admin center.</span></span>

1. <span data-ttu-id="e68d5-118">Dans le Teams d’administration, développez les **paramètres** à l’échelle de l’organisation, puis cliquez **sur Comptes de ressources.**</span><span class="sxs-lookup"><span data-stu-id="e68d5-118">In the Teams admin center, expand **Org-wide settings**, and then click **Resource accounts**.</span></span>

2. <span data-ttu-id="e68d5-119">Cliquez sur **Ajouter**.</span><span class="sxs-lookup"><span data-stu-id="e68d5-119">Click **Add**.</span></span>

3. <span data-ttu-id="e68d5-120">Dans le **volet Ajouter un compte** de ressource, tapez Nom **d’affichage,** Nom d’utilisateur et sélectionnez Le attendant **automatique** pour le type de **compte ressource** </span><span class="sxs-lookup"><span data-stu-id="e68d5-120">In the **Add resource account** pane, fill out **Display name**, **Username**, and choose **Auto attendant** for the **Resource account type**</span></span>

    ![Capture d’écran de l’interface utilisateur Ajouter un compte de ressource](../media/resource-account-add.png)

4. <span data-ttu-id="e68d5-122">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="e68d5-122">Click **Save**.</span></span>

    <span data-ttu-id="e68d5-123">Le nouveau compte apparaît dans la liste des comptes.</span><span class="sxs-lookup"><span data-stu-id="e68d5-123">The new account will appear in the list of accounts.</span></span>

    ![Capture d’écran d’une liste des comptes de ressources](../media/resource-accounts-page.png)

### <a name="assign-a-license"></a><span data-ttu-id="e68d5-125">Attribuer une licence</span><span class="sxs-lookup"><span data-stu-id="e68d5-125">Assign a license</span></span>

<span data-ttu-id="e68d5-126">Vous devez affecter une *Microsoft 365 Système téléphonique - Licence Utilisateur* virtuel au compte de ressource.</span><span class="sxs-lookup"><span data-stu-id="e68d5-126">You must assign a *Microsoft 365 Phone System - Virtual User* license to the resource account.</span></span>

1. <span data-ttu-id="e68d5-127">Dans le Microsoft 365 d’administration, cliquez sur le compte de ressource auquel vous voulez attribuer une licence.</span><span class="sxs-lookup"><span data-stu-id="e68d5-127">In the Microsoft 365 admin center, click the resource account to which you want to assign a license.</span></span>

2. <span data-ttu-id="e68d5-128">Sous **l’onglet Licences et** applications, sous **Licences,** sélectionnez **Microsoft 365 Système téléphonique - Utilisateur virtuel.**</span><span class="sxs-lookup"><span data-stu-id="e68d5-128">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>

3. <span data-ttu-id="e68d5-129">Cliquez **sur Enregistrer les modifications.**</span><span class="sxs-lookup"><span data-stu-id="e68d5-129">Click **Save changes**.</span></span>

    ![Capture d’écran de l’interface utilisateur d’attribution de licences dans Microsoft 365 centre d’administration](../media/resource-account-assign-virtual-user-license.png)

### <a name="assign-a-service-number"></a><span data-ttu-id="e68d5-131">Affecter un numéro de service</span><span class="sxs-lookup"><span data-stu-id="e68d5-131">Assign a service number</span></span>

<span data-ttu-id="e68d5-132">Si vous avez besoin que ce moyen de service automatique soit accessible à l’aide d’un numéro de téléphone, affectez ce numéro au compte de ressource.</span><span class="sxs-lookup"><span data-stu-id="e68d5-132">If you need this auto attendant to be reachable by a phone number, then assign that number to the resource account.</span></span>

1. <span data-ttu-id="e68d5-133">Dans le Teams d’administration, dans la **page** Comptes de ressources, sélectionnez le compte de ressource auquel vous voulez affecter un numéro de service, puis cliquez sur **Affecter/Désaffecter.**</span><span class="sxs-lookup"><span data-stu-id="e68d5-133">In the Teams admin center, on the **Resource accounts** page, select the resource account to which you want to assign a service number, and then click **Assign/unassign**.</span></span>

2. <span data-ttu-id="e68d5-134">Dans la **Téléphone du type de** nombre, choisissez le type de nombre à utiliser.</span><span class="sxs-lookup"><span data-stu-id="e68d5-134">In the **Phone number type** dropdown, choose the type of number that you want to use.</span></span>

3. <span data-ttu-id="e68d5-135">Dans la **zone Numéro de téléphone** affecté, recherchez le numéro à utiliser, puis cliquez sur **Ajouter.**</span><span class="sxs-lookup"><span data-stu-id="e68d5-135">In the **Assigned phone number** box, search for the number you want to use and click **Add**.</span></span>

    ![Capture d’écran de l’interface utilisateur affecter un numéro de service](../media/resource-account-assign-phone-number.png)

4. <span data-ttu-id="e68d5-137">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="e68d5-137">Click **Save**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="e68d5-138">Étape 2 : le attendant automatique - Informations générales sur ></span><span class="sxs-lookup"><span data-stu-id="e68d5-138">Step 2 - Auto attendant general info ></span></span>](?tabs=general-info#steps)

# <a name="step-2brattendant-general-info"></a>[<span data-ttu-id="e68d5-139">Étape 2 : <br> Attendant - Informations générales</span><span class="sxs-lookup"><span data-stu-id="e68d5-139">Step 2<br>Attendant general info</span></span>](#tab/general-info)

<span data-ttu-id="e68d5-140">Pour configurer un attendant automatique</span><span class="sxs-lookup"><span data-stu-id="e68d5-140">To set up an auto attendant</span></span>

1. <span data-ttu-id="e68d5-141">Dans le Teams d’administration, développez **Voix,** cliquez sur **Auto attendants,** puis sur **Ajouter.**</span><span class="sxs-lookup"><span data-stu-id="e68d5-141">In the Teams admin center, expand **Voice**, click **Auto attendants**, and then click **Add**.</span></span>

2. <span data-ttu-id="e68d5-142">Tapez un nom pour le attendant automatique dans la zone en haut.</span><span class="sxs-lookup"><span data-stu-id="e68d5-142">Type a name for the auto attendant in the box at the top.</span></span>

3. <span data-ttu-id="e68d5-143">Si vous voulez désigner un opérateur, spécifiez la destination des appels vers cet opérateur.</span><span class="sxs-lookup"><span data-stu-id="e68d5-143">If you want to designate an operator, specify the destination for calls to the operator.</span></span> <span data-ttu-id="e68d5-144">Cette option est facultative (mais recommandée).</span><span class="sxs-lookup"><span data-stu-id="e68d5-144">This is optional (but recommended).</span></span> <span data-ttu-id="e68d5-145">Vous pouvez définir l’option **Opérateur** pour permettre aux appelants de sortir des menus et de parler à une personne désignée.</span><span class="sxs-lookup"><span data-stu-id="e68d5-145">You can set the **Operator** option to allow callers to break out of the menus and speak to a designated person.</span></span>

4. <span data-ttu-id="e68d5-146">Spécifiez le fuseau horaire de ce attendant automatique.</span><span class="sxs-lookup"><span data-stu-id="e68d5-146">Specify the time zone for this auto attendant.</span></span> <span data-ttu-id="e68d5-147">Le fuseau horaire est utilisé pour calculer les heures d’ouverture si vous créez un flux d’appels distinct pour les heures de travail en de suite.</span><span class="sxs-lookup"><span data-stu-id="e68d5-147">The time zone is used for calculating business hours if you create a separate call flow for after hours.</span></span>

5. <span data-ttu-id="e68d5-148">Spécifiez une langue pour ce attendant automatique.</span><span class="sxs-lookup"><span data-stu-id="e68d5-148">Specify a language for this auto attendant.</span></span> <span data-ttu-id="e68d5-149">Il s’agit de la langue qui sera utilisée pour les invites vocales générées par le système.</span><span class="sxs-lookup"><span data-stu-id="e68d5-149">This is the language that will be used for system-generated voice prompts.</span></span>

6. <span data-ttu-id="e68d5-150">Choisissez si vous voulez activer les entrées vocales.</span><span class="sxs-lookup"><span data-stu-id="e68d5-150">Choose if you want to enable voice inputs.</span></span> <span data-ttu-id="e68d5-151">Lorsqu’elle est activée, le nom de chaque option de menu devient un mot clé de reconnaissance vocale.</span><span class="sxs-lookup"><span data-stu-id="e68d5-151">When enabled, the name of every menu option becomes a speech-recognition keyword.</span></span> <span data-ttu-id="e68d5-152">Par exemple, les appelants peuvent dire « Un » pour sélectionner l’option de menu mappée vers la touche 1, ou dire « Ventes » pour sélectionner l’option de menu appelée « Ventes ».</span><span class="sxs-lookup"><span data-stu-id="e68d5-152">For example, callers can say "One" to select the menu option mapped to key 1, or they can say "Sales" to select the menu option named "Sales."</span></span>

    ![Capture d’écran des paramètres de attendant automatique pour les entrées de nom, d’opérateur, de fuseau horaire, de langue et de voix](../media/auto-attendant-general-info-page-new.png)

7. <span data-ttu-id="e68d5-154">Cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="e68d5-154">Click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="e68d5-155">Étape 3 : flux d’appels ></span><span class="sxs-lookup"><span data-stu-id="e68d5-155">Step 3 - Call flow ></span></span>](?tabs=call-flow#steps)

# <a name="step-3brcall-flow"></a>[<span data-ttu-id="e68d5-156">Flux d’appels <br> d’étape 3</span><span class="sxs-lookup"><span data-stu-id="e68d5-156">Step 3<br>Call flow</span></span>](#tab/call-flow)

<span data-ttu-id="e68d5-157">Choisir vos options de flux d’appels</span><span class="sxs-lookup"><span data-stu-id="e68d5-157">Choose your call flow options</span></span>

1. <span data-ttu-id="e68d5-158">Choisissez si vous voulez lire un message d’accueil lorsque le attendant automatique répond à un appel.</span><span class="sxs-lookup"><span data-stu-id="e68d5-158">Choose if you want to play a greeting when the auto attendant answers a call.</span></span>

    <span data-ttu-id="e68d5-159">Si vous **sélectionnez Lire un** fichier audio, vous pouvez utiliser le bouton **Télécharger** fichier pour télécharger un message d’accueil enregistré en tant qu’audio dans . WAV, .MP3, ou . Format WMA.</span><span class="sxs-lookup"><span data-stu-id="e68d5-159">If you select **Play an audio file** you can use the **Upload file** button to upload a recorded greeting message saved as audio in .WAV, .MP3, or .WMA format.</span></span> <span data-ttu-id="e68d5-160">L’enregistrement ne peut pas avoir une taille supérieure à 5 Mo.</span><span class="sxs-lookup"><span data-stu-id="e68d5-160">The recording can be no larger than 5 MB.</span></span>

    <span data-ttu-id="e68d5-161">Si vous sélectionnez Taper un **message** de salutation, le système lit le texte que vous tapez (jusqu’à 1 000 caractères) lorsque le attendant automatique répond à un appel.</span><span class="sxs-lookup"><span data-stu-id="e68d5-161">If you select **Type a greeting message** the system will read the text you the text that you type (up to 1000 characters) when the auto attendant answers a call.</span></span>

    ![Capture d’écran des paramètres de message d’accueil](../media/auto-attendant-call-flow-greeting-message.png)

2. <span data-ttu-id="e68d5-163">Choisissez la façon dont vous voulez router l’appel.</span><span class="sxs-lookup"><span data-stu-id="e68d5-163">Choose how you want to route the call.</span></span>

    <span data-ttu-id="e68d5-164">Si vous sélectionnez **Déconnecter,** le attendant automatique raccrochera.</span><span class="sxs-lookup"><span data-stu-id="e68d5-164">If you select **Disconnect**, the auto attendant will hang up the call.</span></span>

    <span data-ttu-id="e68d5-165">Si vous sélectionnez **Rediriger l’appel,** vous pouvez choisir l’une des destinations de routage des appels.</span><span class="sxs-lookup"><span data-stu-id="e68d5-165">If you select **Redirect call**, you can choose one of the call routing destinations.</span></span>

    <span data-ttu-id="e68d5-166">Si vous sélectionnez **les options du menu** Lecture, vous pouvez choisir de lire un fichier **audio** ou de taper un **message** d’accueil, puis de choisir entre les options de menu et la recherche dans l’annuaire.</span><span class="sxs-lookup"><span data-stu-id="e68d5-166">If you select **Play menu options**, you can choose to **Play an audio file** or **Type in a greeting message** and then choose between menu options and directory search.</span></span>

    ![Capture d’écran des paramètres de routage des appels](../media/auto-attendant-call-flow-route-call-message.png)

3. <span data-ttu-id="e68d5-168">Si vous souhaitez que les appelants utilisent les touches de numérotation pour naviguer, sous Définir les options du **menu,** choisissez ce que vous voulez faire lorsque les appelants appuient sur une touche de numérotation.</span><span class="sxs-lookup"><span data-stu-id="e68d5-168">If you want callers to use dial keys to navigate, then under **Set menu options**, choose what you want to happen when callers press a dial key.</span></span> <span data-ttu-id="e68d5-169">(Si vous créez ce attendant automatique en tant qu’annuaire de l’entreprise, laissez les options de touche de numérotation vides.)</span><span class="sxs-lookup"><span data-stu-id="e68d5-169">(If you're creating this auto attendant as a company directory, leave the dial key options blank.)</span></span>

    <span data-ttu-id="e68d5-170">Vous pouvez définir n’importe quelle touche de numérotation sur les destinations suivantes :</span><span class="sxs-lookup"><span data-stu-id="e68d5-170">You can set any of the dial keys to the following destinations:</span></span>

    - <span data-ttu-id="e68d5-171">**Une personne de l’organisation,** une personne de votre organisation qui peut recevoir des appels vocux.</span><span class="sxs-lookup"><span data-stu-id="e68d5-171">**Person in the organization** - a person in your organization who is able to receive voice calls.</span></span>
    - <span data-ttu-id="e68d5-172">**Application vocale :** un autre service de messagerie automatique ou une file d’attente d’appels.</span><span class="sxs-lookup"><span data-stu-id="e68d5-172">**Voice app** - another auto attendant or a call queue.</span></span>
    - <span data-ttu-id="e68d5-173">**Numéro de téléphone externe -** n’importe quel numéro de téléphone.</span><span class="sxs-lookup"><span data-stu-id="e68d5-173">**External phone number** - any phone number.</span></span> <span data-ttu-id="e68d5-174">Utilisez ce format : +[code pays][code de zone][numéro de téléphone]</span><span class="sxs-lookup"><span data-stu-id="e68d5-174">Use this format: +[country code][area code][phone number]</span></span>
    - <span data-ttu-id="e68d5-175">**Messagerie vocale** (boîte vocale associée à Microsoft 365 groupe de messagerie vocale que vous spécifiez.</span><span class="sxs-lookup"><span data-stu-id="e68d5-175">**Voicemail** - the voice mailbox associated with a Microsoft 365 group that you specify.</span></span>
    - <span data-ttu-id="e68d5-176">**Opérateur** (opérateur défini pour le transport automatique).</span><span class="sxs-lookup"><span data-stu-id="e68d5-176">**Operator** - the operator defined for the auto attendant.</span></span> <span data-ttu-id="e68d5-177">La définition d’un opérateur est facultative.</span><span class="sxs-lookup"><span data-stu-id="e68d5-177">Defining an operator is optional.</span></span> <span data-ttu-id="e68d5-178">L’opérateur peut être défini comme n’importe quelle autre destination dans cette liste.</span><span class="sxs-lookup"><span data-stu-id="e68d5-178">The operator can be defined as any of the other destinations in this list.</span></span>

    <span data-ttu-id="e68d5-179">Nous vous recommandons de définir 0 touche sur l’opérateur.</span><span class="sxs-lookup"><span data-stu-id="e68d5-179">We recommend setting 0 key to the operator.</span></span>

    <span data-ttu-id="e68d5-180">Pour chaque option de menu, spécifiez les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="e68d5-180">For each menu option, specify the following:</span></span>

    - <span data-ttu-id="e68d5-181">**Touche de numérotation** (clé du clavier téléphonique pour accéder à cette option).</span><span class="sxs-lookup"><span data-stu-id="e68d5-181">**Dial key** - the key on the telephone keypad to access this option.</span></span>

    - <span data-ttu-id="e68d5-182">**Commande vocale** : définit la commande vocale qu’un appelant peut lui donner pour accéder à cette option, si les entrées vocales sont activées.</span><span class="sxs-lookup"><span data-stu-id="e68d5-182">**Voice command** - defines the voice command that a caller can give to access this option, if voice inputs are enabled.</span></span> <span data-ttu-id="e68d5-183">Il peut contenir plusieurs mots tels que « Service clientèle » ou « Activités et activités ».</span><span class="sxs-lookup"><span data-stu-id="e68d5-183">It can contain multiple words like "Customer Service" or "Operations and Grounds."</span></span> 

    - <span data-ttu-id="e68d5-184">**Redirigez** vers l’endroit où vous souhaitez que l’appel soit reçu lorsque les appelants choisissent cette option.</span><span class="sxs-lookup"><span data-stu-id="e68d5-184">**Redirect to** - where you want the call to go when callers choose this option.</span></span> <span data-ttu-id="e68d5-185">Si vous redirigez vers un service de service automatique ou une file d’attente d’appels, sélectionnez le compte de ressource qui lui est associé.</span><span class="sxs-lookup"><span data-stu-id="e68d5-185">If you are redirecting to an auto attendant or call queue, choose the resource account associated with it.</span></span>

    ![Capture d’écran des options de touches de numérotation](../media/auto-attendant-call-flow-menu-options-complete.png)

4. <span data-ttu-id="e68d5-187">Si vous souhaitez utiliser ce attendant automatique comme annuaire de l’entreprise, sous Recherche dans l’annuaire, **sélectionnez Composer par nom.**</span><span class="sxs-lookup"><span data-stu-id="e68d5-187">If you want to use this auto attendant as a company directory, then under **Directory search**, select **Dial by name**.</span></span> <span data-ttu-id="e68d5-188">Lorsque vous activez cette option, les appelants peuvent dire le nom de l’utilisateur ou le taper sur le clavier du téléphone.</span><span class="sxs-lookup"><span data-stu-id="e68d5-188">When you enable this option, callers can say the user's name or type it on the telephone keypad.</span></span> <span data-ttu-id="e68d5-189">Tout utilisateur en ligne titulaire Système téléphonique licence est un utilisateur éligible et peut être trouvé avec la numérotation par nom.</span><span class="sxs-lookup"><span data-stu-id="e68d5-189">Any online user with a Phone System license is an eligible user and can be found with Dial by name.</span></span> 

    <span data-ttu-id="e68d5-190">(Vous pouvez choisir **Numérotation par extension,** mais l’extension doit être configurée dans Azure Active Directory.)</span><span class="sxs-lookup"><span data-stu-id="e68d5-190">(You can choose **Dial by extension**, however the extension must be configured in Azure Active Directory.)</span></span>

5. <span data-ttu-id="e68d5-191">Une fois que vous avez sélectionné une option **de recherche dans l’annuaire,** cliquez sur **Suivant.**</span><span class="sxs-lookup"><span data-stu-id="e68d5-191">Once you have selected a **Directory search** option, click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="e68d5-192">Étape 4 : flux d’appels en de suite après ></span><span class="sxs-lookup"><span data-stu-id="e68d5-192">Step 4 - After hours call flow ></span></span>](?tabs=after-hours#steps)

# <a name="step-4brafter-hours"></a>[<span data-ttu-id="e68d5-193">Étape 4 Après <br> les heures de travail</span><span class="sxs-lookup"><span data-stu-id="e68d5-193">Step 4<br>After hours</span></span>](#tab/after-hours)

<span data-ttu-id="e68d5-194">Les heures d’ouverture peuvent être définies pour chaque employé de service automatique.</span><span class="sxs-lookup"><span data-stu-id="e68d5-194">Business hours can be set for each auto attendant.</span></span> <span data-ttu-id="e68d5-195">Si ce n'est pas le cas, tous les jours et toutes les heures de la semaine seront considérés comme heures d'ouverture, car une planification 24/24 est définie par défaut.</span><span class="sxs-lookup"><span data-stu-id="e68d5-195">If business hours aren't set, all days and all hours in the day are considered business hours because a 24/7 schedule is set by default.</span></span> <span data-ttu-id="e68d5-196">Les heures d’ouverture peuvent être définies avec des pauses au cours de la journée et toutes les heures non définies comme heures d’ouverture sont considérées comme des heures d’ouverture en de suite.</span><span class="sxs-lookup"><span data-stu-id="e68d5-196">Business hours can be set with breaks in time during the day, and all of the hours that are not set as business hours are considered after-hours.</span></span> <span data-ttu-id="e68d5-197">Vous pouvez définir différentes options de traitement des appels entrants et des messages d’accueil pour les heures de travail en de suite.</span><span class="sxs-lookup"><span data-stu-id="e68d5-197">You can set different incoming call-handling options and greetings for after-hours.</span></span>

<span data-ttu-id="e68d5-198">Selon la configuration de vos files d’attente et de vos files d’attente automatiques, il se peut que vous devrez uniquement spécifier le routage des appels en de après-heures pour les travailleurs automatiques avec des numéros de téléphone directs.</span><span class="sxs-lookup"><span data-stu-id="e68d5-198">Depending on how you have configured your auto attendants and call queues, you may only need to specify after-hours call routing for auto attendants with direct phone numbers.</span></span>

<span data-ttu-id="e68d5-199">Si vous souhaitez un routage d’appel distinct pour les appelants en de suite, spécifiez vos heures d’ouverture pour chaque jour.</span><span class="sxs-lookup"><span data-stu-id="e68d5-199">If you want separate call routing for after-hours callers, then specify your business hours for each day.</span></span> <span data-ttu-id="e68d5-200">Cliquez **sur Ajouter un nouvel horaire** pour spécifier plusieurs ensembles d’heures pour un jour donné, par exemple, pour spécifier une pause déjeuner.</span><span class="sxs-lookup"><span data-stu-id="e68d5-200">Click **Add new time** to specify multiple sets of hours for a given day, for example, to specify a lunch break.</span></span>

![Capture d’écran des paramètres de jour et d’heure de fin](../media/auto-attendant-business-hours.png)

<span data-ttu-id="e68d5-202">Une fois que vous avez spécifié vos heures d’ouverture, choisissez vos options de routage des appels pour les heures de fermeture.</span><span class="sxs-lookup"><span data-stu-id="e68d5-202">Once you have specified your business hours, then choose your call routing options for after hours.</span></span> <span data-ttu-id="e68d5-203">Les mêmes options sont disponibles que pour le routage des appels pendant les heures d’ouverture que vous avez spécifié à l’étape **3 (Flux d’appels).**</span><span class="sxs-lookup"><span data-stu-id="e68d5-203">The same options are available as for the business hours call routing that you specified in **Step 3 - Call flow**.</span></span>

<span data-ttu-id="e68d5-204">Cliquez **sur Suivant** lorsque vous avez terminé.</span><span class="sxs-lookup"><span data-stu-id="e68d5-204">Click **Next** when you're done.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="e68d5-205">Étape 5 : flux d’appels pour les ></span><span class="sxs-lookup"><span data-stu-id="e68d5-205">Step 5 - Holiday call flow ></span></span>](?tabs=holidays#steps)

# <a name="step-5brholidays"></a>[<span data-ttu-id="e68d5-206">Étape 5 <br> Jours fériés</span><span class="sxs-lookup"><span data-stu-id="e68d5-206">Step 5<br>Holidays</span></span>](#tab/holidays)

<span data-ttu-id="e68d5-207">Vous pouvez faire router les appels vers votre service de service automatique différemment les jours fériés et les autres jours.</span><span class="sxs-lookup"><span data-stu-id="e68d5-207">You can have calls to your auto attendant routed differently on holidays than on other days.</span></span> <span data-ttu-id="e68d5-208">(Si vous ne voulez pas utiliser un flux d’appels différent pour les jours fériés, vous pouvez ignorer cette étape.)</span><span class="sxs-lookup"><span data-stu-id="e68d5-208">(If you don't want to have a different call flow for holidays, you can skip this step.)</span></span>

<span data-ttu-id="e68d5-209">Votre employé automatique peut avoir un flux d’appels pour chaque jour férié que vous avez installé.</span><span class="sxs-lookup"><span data-stu-id="e68d5-209">Your auto attendant can have a call flow for each holiday you've set up.</span></span> <span data-ttu-id="e68d5-210">Vous pouvez ajouter jusqu'à 20 congés planifiés pour chaque standard automatique.</span><span class="sxs-lookup"><span data-stu-id="e68d5-210">You can add up to 20 scheduled holidays to each auto attendant.</span></span>

1. <span data-ttu-id="e68d5-211">Dans la page Paramètres d’appel pour les fêtes, cliquez **sur Ajouter.**</span><span class="sxs-lookup"><span data-stu-id="e68d5-211">On the Holiday call settings page, click **Add**.</span></span>

2. <span data-ttu-id="e68d5-212">Tapez un nom pour ce paramètre de congés.</span><span class="sxs-lookup"><span data-stu-id="e68d5-212">Type a name for this holiday setting.</span></span>

3. <span data-ttu-id="e68d5-213">Dans la **dropdown** Jours fériés, choisissez les jours fériés que vous voulez utiliser.</span><span class="sxs-lookup"><span data-stu-id="e68d5-213">From the **Holiday** dropdown, choose the holiday that you want to use.</span></span>

4. <span data-ttu-id="e68d5-214">Choisissez le type de message d’accueil que vous voulez utiliser.</span><span class="sxs-lookup"><span data-stu-id="e68d5-214">Choose the type of greeting that you want to use.</span></span>

    ![Capture d’écran des paramètres de vœux pour les fêtes de fin d’année](../media/auto-attendant-holiday-greeting.png)

5. <span data-ttu-id="e68d5-216">Choisissez si vous voulez **déconnecter ou** **rediriger** l’appel.</span><span class="sxs-lookup"><span data-stu-id="e68d5-216">Choose if you want to **Disconnect** or **Redirect** the call.</span></span>

6. <span data-ttu-id="e68d5-217">Si vous choisissez de rediriger l’appel, choisissez sa destination de routage.</span><span class="sxs-lookup"><span data-stu-id="e68d5-217">If you chose to redirect, choose the call routing destination for the call.</span></span>

    ![Capture d’écran des paramètres d’action d’appel pour les fêtes](../media/auto-attendant-holiday-actions.png)

7. <span data-ttu-id="e68d5-219">Cliquez sur **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="e68d5-219">Click **Save**.</span></span>

    <span data-ttu-id="e68d5-220">Répétez la procédure si nécessaire pour chaque jour férié supplémentaire.</span><span class="sxs-lookup"><span data-stu-id="e68d5-220">Repeat the procedure as needed for each additional holiday.</span></span>

    ![Capture d’écran des paramètres de congés avec jours fériés répertoriés](../media/auto-attendant-holiday-call-settings.png)

    <span data-ttu-id="e68d5-222">Une fois que vous avez ajouté tous vos jours fériés, cliquez sur **Suivant.**</span><span class="sxs-lookup"><span data-stu-id="e68d5-222">When you've added all your holidays, click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="e68d5-223">Étape 6 : choisir qui fait partir du répertoire ></span><span class="sxs-lookup"><span data-stu-id="e68d5-223">Step 6 - Choose who's in the directory ></span></span>](?tabs=dial-scope#steps)

# <a name="step-6brdirectory-members"></a>[<span data-ttu-id="e68d5-224">Étape 6 <br> Membres du répertoire</span><span class="sxs-lookup"><span data-stu-id="e68d5-224">Step 6<br>Directory members</span></span>](#tab/dial-scope)

<span data-ttu-id="e68d5-225">*L’étendue de* la numérotation définit les utilisateurs disponibles dans l’annuaire lorsqu’un appelant utilise la numérotation par nom ou la numérotation par extension.</span><span class="sxs-lookup"><span data-stu-id="e68d5-225">The *dial scope* defines which users are available in the directory when a caller uses dial-by-name or dial-by-extension.</span></span> <span data-ttu-id="e68d5-226">La valeur par défaut de **Tous les utilisateurs en ligne** inclut tous les utilisateurs de votre organisation qui sont des utilisateurs en ligne Système téléphonique licence utilisateur.</span><span class="sxs-lookup"><span data-stu-id="e68d5-226">The default of **All online users** includes all users in your organization that are Online users with a Phone System license.</span></span>

<span data-ttu-id="e68d5-227">Vous pouvez inclure ou exclure  des utilisateurs  spécifiques en sélectionnant Groupe d’utilisateurs personnalisés sous Inclure ou Exclure, et en choisissant un ou plusieurs groupes de Microsoft 365, listes de distribution ou groupes de sécurité. </span><span class="sxs-lookup"><span data-stu-id="e68d5-227">You can include or exclude specific users by selecting **Custom user group** under **Include** or **Exclude** and choosing one or more Microsoft 365 groups, distribution lists, or security groups.</span></span> <span data-ttu-id="e68d5-228">Par exemple, vous pouvez exclure des cadres de votre organisation de l’annuaire d’appels.</span><span class="sxs-lookup"><span data-stu-id="e68d5-228">For example, you might want to exclude executives in your organization from the dialing directory.</span></span> <span data-ttu-id="e68d5-229">(Si un utilisateur se trouve dans les deux listes, il sera exclu de l’annuaire.)</span><span class="sxs-lookup"><span data-stu-id="e68d5-229">(If a user is in both lists, they will be excluded from the directory.)</span></span>

![Capture d’écran de l’étendue de la numérotation : inclure et exclure des options](../media/auto-attendant-dial-scope.png)

> [!NOTE]
> <span data-ttu-id="e68d5-231">Jusqu’à 36 heures peuvent être nécessaire pour que le nom d’un nouvel utilisateur soit répertorié dans l’annuaire.</span><span class="sxs-lookup"><span data-stu-id="e68d5-231">It might take up to 36 hours for a new user to have their name listed in the directory.</span></span>

<span data-ttu-id="e68d5-232">Lorsque vous avez terminé de définir la portée de la numérotation, cliquez sur **Suivant.**</span><span class="sxs-lookup"><span data-stu-id="e68d5-232">When you're done setting the dial scope, click **Next**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="e68d5-233">Étape 7 : affecter un compte de ressource ></span><span class="sxs-lookup"><span data-stu-id="e68d5-233">Step 7 - Assign a resource account ></span></span>](?tabs=resource-accounts#steps)

# <a name="step-7brresource-accounts"></a>[<span data-ttu-id="e68d5-234">Étape 7 <br> : comptes de ressources</span><span class="sxs-lookup"><span data-stu-id="e68d5-234">Step 7<br>Resource accounts</span></span>](#tab/resource-accounts)

<span data-ttu-id="e68d5-235">Tous les attendants automatiques doivent avoir un compte de ressource associé.</span><span class="sxs-lookup"><span data-stu-id="e68d5-235">All auto attendants must have an associated resource account.</span></span>  <span data-ttu-id="e68d5-236">Les travailleurs automatiques de premier niveau auront besoin d’au moins un compte de ressource associé à un numéro de service.</span><span class="sxs-lookup"><span data-stu-id="e68d5-236">First level auto attendants will need at least one resource account that has an associated service number.</span></span> <span data-ttu-id="e68d5-237">Si vous le souhaitez, vous pouvez affecter plusieurs comptes de ressources à un service automatique, chacun avec un numéro de service distinct.</span><span class="sxs-lookup"><span data-stu-id="e68d5-237">If you wish, you can assign several resource accounts to an auto attendant, each with a separate service number.</span></span>

<span data-ttu-id="e68d5-238">Pour ajouter un compte de ressource</span><span class="sxs-lookup"><span data-stu-id="e68d5-238">To add a resource account</span></span>

1. <span data-ttu-id="e68d5-239">Cliquez **sur** Ajouter et recherchez le compte à ajouter.</span><span class="sxs-lookup"><span data-stu-id="e68d5-239">Click **Add** and search for the account that you want to add.</span></span> <span data-ttu-id="e68d5-240">Cliquez **sur** Ajouter, puis sur **Ajouter.**</span><span class="sxs-lookup"><span data-stu-id="e68d5-240">Click **Add**, and then click **Add**.</span></span>

    ![Capture d’écran du panneau Ajouter des comptes du compte de ressources](../media/auto-attendant-add-resource-account.png)

2. <span data-ttu-id="e68d5-242">Lorsque vous avez terminé d’ajouter des comptes de service, cliquez sur **Envoyer.**</span><span class="sxs-lookup"><span data-stu-id="e68d5-242">When you have finished adding service accounts, click **Submit**.</span></span>

    ![Capture d’écran d’une liste de comptes de ressources affichant le compte de ressource avec le numéro de service affecté](../media/auto-attendant-resource-account-assigned.png)

    <span data-ttu-id="e68d5-244">La configuration du attendant automatique est terminée.</span><span class="sxs-lookup"><span data-stu-id="e68d5-244">This completes the auto attendant configuration.</span></span>

---
