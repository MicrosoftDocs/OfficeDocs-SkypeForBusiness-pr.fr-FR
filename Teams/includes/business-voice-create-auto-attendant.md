#### <a name="video-demonstration"></a>Démonstration vidéo

Cette vidéo montre un exemple de base de la création d’un attendant automatique dans Microsoft Teams.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWEnCG?autoplay=false]

#### <a name="before-you-begin"></a>Avant de commencer

Obtenez les numéros de service (les numéros de service sont un type spécial de numéro de téléphone utilisé par les agents automatiques) dont vous avez besoin pour les numéros de service automatiques que vous souhaitez rendre accessibles en composant un numéro direct depuis l’extérieur de votre organisation. Cela peut inclure [le transfert de numéros d’un autre fournisseur](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md) ou [la demande de nouveaux numéros de service](../getting-service-phone-numbers.md).

Chaque standard automatique doit être affecté à un *utilisateur Microsoft Teams Téléphone standard - Utilisateur* virtuel. Lorsque vous avez acheté Teams Téléphone Standard ou Teams Téléphone avec des licences d’offre groupée de forfait d’appels, vous avez également reçu un certain nombre de licences *Microsoft Teams Téléphone Standard - Utilisateur* virtuel. Vous n’avez donc probablement pas besoin d’en demander davantage. Toutefois, si vous en avez besoin à l’avenir, vous pouvez les obtenir en suivant les instructions de la [licence Teams Téléphone Standard - Utilisateur virtuel](../teams-add-on-licensing/virtual-user.md).

Si vous souhaitez utiliser un itinéraire des appels différent pour les jours fériés, [](../set-up-holidays-in-teams.md) créez les jours fériés que vous voulez utiliser avant de créer le attendant automatique.

<a name="steps"></a>

#### <a name="follow-these-steps-to-set-up-your-auto-attendant"></a>Pour configurer votre attendant automatique, suivez les étapes ci-après

# <a name="step-1---phone-number"></a>[Étape 1 : Téléphone numéro](#tab/phone-number)

> [!NOTE]
> Si vous devez configurer la Teams Système téléphonique avec l’offre groupée de forfaits d’appels pour la première fois et que vous en êtes à l’étape **6** : configurer un attendant automatique pour le numéro de téléphone principal de votre entreprise, vous avez déjà terminé les étapes de cet onglet. Passer à l’onglet suivant : informations générales sur le [attendant](?tabs=general-info#steps) automatique.

Chaque employé automatique que vous créez nécessite un compte de ressource. Ce compte est similaire à un compte d’utilisateur, sauf qu’il est associé à un moyen de service automatique ou à une file d’attente d’appels au lieu d’une personne. Dans cette étape, nous allons créer le compte, lui attribuer *Microsoft Teams Téléphone licence Utilisateur virtuel Standard*, puis affecter un numéro de service.

### <a name="create-a-resource-account"></a>Créer un compte de ressource

Vous pouvez créer un compte de ressource dans le Teams d’administration.

1. Dans le Teams d’administration, développez les **paramètres** à l’échelle de l’organisation, puis cliquez **sur Comptes de ressources**.

2. Cliquez sur **Ajouter**.

3. Dans le **volet Ajouter un compte** de ressource, tapez **Nom d’affichage****, Nom** d’utilisateur et sélectionnez **Le attendant automatique** pour le **type de compte de ressource**

4. Cliquez sur **Enregistrer**.

    Le nouveau compte apparaît dans la liste des comptes.

### <a name="assign-a-license"></a>Attribuer une licence

Vous devez affecter une *licence Microsoft Teams Téléphone virtuel Standard - Utilisateur* virtuel au compte de ressource.

1. Dans la Centre d'administration Microsoft 365, cliquez sur le compte de ressource auquel vous voulez attribuer une licence.

2. Sous **l’onglet Licences et** applications, sous **Licences**, sélectionnez **Microsoft Teams Téléphone Standard - Utilisateur virtuel**.

3. Cliquez sur **Enregistrer les modifications**.

### <a name="assign-a-service-number"></a>Affecter un numéro de service

Si vous avez besoin que ce moyen de service automatique soit accessible à l’aide d’un numéro de téléphone, affectez ce numéro au compte de ressource.

1. Dans le Teams d’administration, dans **la page Comptes** de ressources, sélectionnez le compte de ressource auquel vous voulez affecter un numéro de service, puis cliquez sur **Affecter/Désaffecter**.

2. Dans la **Téléphone du type de** nombre, choisissez le type de nombre à utiliser.

3. Dans la **zone Numéro de téléphone** affecté, recherchez le numéro à utiliser, puis cliquez sur **Ajouter**.

4. Cliquez sur **Enregistrer**.

> [!div class="nextstepaction"]
> [Étape 2 : le attendant automatique - Informations générales sur >](?tabs=general-info#steps)

# <a name="step-2---attendant-general-info"></a>[Étape 2 - Informations générales sur Attendant](#tab/general-info)

Pour configurer un attendant automatique

1. Dans le Teams d’administration, développez **Voix**, cliquez sur **Auto attendants**, puis sur **Ajouter**.

2. Tapez un nom pour le attendant automatique dans la zone en haut.

3. Si vous voulez désigner un opérateur, spécifiez la destination des appels vers cet opérateur. Cette option est facultative (mais recommandée). Vous pouvez définir l’option **Opérateur** pour permettre aux appelants de sortir des menus et de parler à une personne désignée.

4. Spécifiez le fuseau horaire de ce attendant automatique. Le fuseau horaire est utilisé pour calculer les heures d’ouverture si vous créez un flux d’appels distinct pour les heures de travail en de suite.

5. Spécifiez une [langue prise en](../create-a-phone-system-auto-attendant-languages.md) charge pour ce attendant automatique. Il s’agit de la langue qui sera utilisée pour les invites vocales générées par le système.

6. Choisissez si vous voulez activer les entrées vocales. Lorsqu’elle est activée, le nom de chaque option de menu devient un mot clé de reconnaissance vocale. Par exemple, les appelants peuvent dire « Un » pour sélectionner l’option de menu mappée vers la touche 1, ou dire « Ventes » pour sélectionner l’option de menu appelée « Ventes ».

7. Cliquez sur **Suivant**.

> [!div class="nextstepaction"]
> [Étape 3 : flux d’appels >](?tabs=call-flow#steps)

# <a name="step-3---call-flow"></a>[Étape 3 : flux d’appels](#tab/call-flow)

Choisir vos options de flux d’appels

1. Choisissez si vous souhaitez lire un message d’accueil lorsque le attendant automatique répond à un appel.

    Si vous **sélectionnez Lire un fichier audio**, vous pouvez utiliser le **bouton Télécharger fichier** pour télécharger un message d’accueil enregistré en tant qu’audio dans . WAV, .MP3, ou . Format WMA. L’enregistrement ne peut pas avoir une taille supérieure à 5 Mo.

    Si vous sélectionnez Taper un **message** de salutation, le système lit le texte que vous tapez (jusqu’à 1 000 caractères) lorsque le attendant automatique répond à un appel.

2. Choisissez la façon dont vous voulez router l’appel.

    Si vous sélectionnez **Déconnecter**, le attendant automatique raccrochera.

    Si vous sélectionnez **Rediriger l’appel**, vous pouvez choisir l’une des destinations de routage des appels.

    Si vous sélectionnez **les options du menu** Lecture, vous pouvez choisir de lire un fichier **audio** ou de taper un **message** d’accueil, puis de choisir entre les options de menu et la recherche dans l’annuaire.

3. Si vous souhaitez que les appelants utilisent les touches de numérotation pour naviguer, sous Définir les **options du menu**, choisissez ce que vous voulez faire lorsque les appelants appuient sur une touche de numérotation. (Si vous créez ce attendant automatique en tant qu’annuaire de l’entreprise, laissez les options de touches de numérotation vides.)

    Vous pouvez définir n’importe quelle touche de numérotation sur les destinations suivantes :

    - **Une personne de l’organisation** , une personne de votre organisation qui peut recevoir des appels vocux.
    - **Application vocale :** un autre attendant automatique ou une file d’attente d’appels.
    - **Numéro de téléphone externe :** n’importe quel numéro de téléphone. Utilisez ce format : +[code pays][code de zone][numéro de téléphone]
    - **Messagerie vocale** : boîte vocale associée à Microsoft 365 groupe de messagerie que vous spécifiez. Vous pouvez choisir si vous voulez des transcriptions de messages vocaux et le message « Veuillez laisser un message après le ton ». invite système.
    - **Opérateur** (opérateur défini pour le transport automatique). La définition d’un opérateur est facultative. L’opérateur peut être défini comme n’importe quelle autre destination dans cette liste.

    Nous vous recommandons de définir 0 touche sur l’opérateur.

    Pour chaque option de menu, spécifiez les éléments suivants :

    - **Touche de numérotation** (clé du clavier téléphonique pour accéder à cette option).

    - **Commande vocale** : définit la commande vocale qu’un appelant peut lui donner pour accéder à cette option, si les entrées vocales sont activées. Il peut contenir plusieurs mots tels que « Service clientèle » ou « Activités et activités ». 

    - **Rediriger** vers l’endroit où vous souhaitez que l’appel soit reçu lorsque les appelants choisissent cette option. Si vous redirigez vers un service de service automatique ou une file d’attente d’appels, sélectionnez le compte de ressource qui lui est associé.

4. Si vous souhaitez utiliser ce attendant automatique comme annuaire de l’entreprise, sous Recherche dans l’annuaire **,** **sélectionnez Composer par nom**. Lorsque vous activez cette option, les appelants peuvent dire le nom de l’utilisateur ou le taper sur le clavier du téléphone. Tout utilisateur en ligne  titulaire Système téléphonique licence est un utilisateur éligible et peut être trouvé avec la numérotation par nom.

    (Vous pouvez choisir **Numérotation par extension**, mais l’extension doit être configurée dans Azure Active Directory.)

5. Une fois que vous avez sélectionné une option **de recherche dans l’annuaire** , cliquez sur **Suivant**.

> [!div class="nextstepaction"]
> [Étape 4 : flux d’appels en de après>](?tabs=after-hours#steps)

# <a name="step-4---after-hours"></a>[Étape 4 : après les heures de travail](#tab/after-hours)

Les heures d’ouverture peuvent être définies pour chaque attendant automatique. Si ce n'est pas le cas, tous les jours et toutes les heures de la semaine seront considérés comme heures d'ouverture, car une planification 24/24 est définie par défaut. Les heures d’ouverture peuvent être définies avec des pauses au cours de la journée et toutes les heures non définies comme heures d’ouverture sont considérées comme des heures d’ouverture en de suite. Vous pouvez définir différentes options de traitement des appels entrants et des messages d’accueil pour les heures de travail en de suite.

Selon la configuration de vos files d’attente automatiques et de vos files d’attente, il se peut que vous devrez uniquement spécifier le routage des appels en de après-heures pour les travailleurs automatiques avec des numéros de téléphone directs.

Si vous souhaitez un routage d’appel distinct pour les appelants en de suite, spécifiez vos heures d’ouverture pour chaque jour. Cliquez **sur Ajouter un nouvel** horaire pour spécifier plusieurs ensembles d’heures pour une journée donnée, par exemple, pour spécifier une pause déjeuner.

Une fois que vous avez spécifié vos heures d’ouverture, sélectionnez vos options de routage des appels pour les heures de fermeture. Les mêmes options sont disponibles que pour le routage des appels pendant les heures d’ouverture que vous avez spécifié à **l’étape 3 (flux d’appels**).

Cliquez **sur Suivant** lorsque vous avez terminé.

> [!div class="nextstepaction"]
> [Étape 5 : flux d’appels pour les >](?tabs=holidays#steps)

# <a name="step-5---holidays"></a>[Étape 5 - Jours fériés](#tab/holidays)

Vous pouvez faire router les appels vers votre service de service automatique différemment les jours fériés et les autres jours. (Si vous ne voulez pas avoir un flux d’appels différent pour les jours fériés, vous pouvez ignorer cette étape.)

Votre employé automatique peut avoir un flux d’appels pour chaque jour férié que vous avez installé. Vous pouvez ajouter jusqu'à 20 congés planifiés pour chaque standard automatique.

1. Dans la page Paramètres d’appel pour les fêtes, cliquez **sur Ajouter**.

2. Tapez un nom pour ce paramètre de congés.

3. Dans **la** dropdown Jours fériés, choisissez les jours fériés que vous voulez utiliser.

4. Choisissez le type de message d’accueil que vous voulez utiliser.

5. Choisissez si vous voulez **déconnecter ou** **rediriger l’appel** .

6. Si vous choisissez de rediriger l’appel, choisissez sa destination de routage.

7. Cliquez sur **Enregistrer**.

    Répétez la procédure si nécessaire pour chaque jour férié supplémentaire.

    Une fois que vous avez ajouté tous vos jours fériés, cliquez sur **Suivant**.

> [!div class="nextstepaction"]
> [Étape 6 : choisir les personnes qui font ou non >](?tabs=dial-scope#steps)

# <a name="step-6---directory-members"></a>[Étape 6 : membres du répertoire](#tab/dial-scope)

*L’étendue de* la numérotation définit les utilisateurs disponibles dans l’annuaire lorsqu’un appelant utilise la numérotation par nom ou la numérotation par extension. La valeur par défaut de **Tous les utilisateurs en** ligne inclut tous les utilisateurs de votre organisation qui sont des utilisateurs en ligne Teams Téléphone licence utilisateur.

Vous pouvez inclure ou exclure des utilisateurs spécifiques en sélectionnant  Groupe d’utilisateurs personnalisés sous Inclure ou Exclure, puis en choisissant un ou plusieurs groupes Microsoft 365, listes de distribution ou groupes de sécurité.  Par exemple, vous pouvez exclure des cadres de votre organisation de l’annuaire d’appels. (Si un utilisateur se trouve dans les deux listes, il sera exclu de l’annuaire.)

> [!NOTE]
> Jusqu’à 36 heures peuvent être nécessaire pour que le nom d’un nouvel utilisateur soit répertorié dans l’annuaire.

Lorsque vous avez terminé de définir la portée de la numérotation, cliquez sur **Suivant**.

> [!div class="nextstepaction"]
> [Étape 7 : affecter un compte de ressource >](?tabs=resource-accounts#steps)

# <a name="step-7---resource-accounts"></a>[Étape 7 : comptes de ressources](#tab/resource-accounts)

Tous les attendants automatiques doivent avoir un compte de ressource associé.  Les travailleurs automatiques de premier niveau auront besoin d’au moins un compte de ressource associé à un numéro de service. Si vous le souhaitez, vous pouvez affecter plusieurs comptes de ressources à un fournisseur de services automatique, chacun avec un numéro de service distinct.

Pour ajouter un compte de ressource

1. Cliquez **sur** Ajouter et recherchez le compte à ajouter. Cliquez **sur Ajouter**, puis sur **Ajouter**.

2. Lorsque vous avez terminé d’ajouter des comptes de service, cliquez sur **Envoyer**.

    La configuration du attendant automatique est terminée.

---
