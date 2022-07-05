Dans Microsoft Teams, un compte de ressource est requis pour chaque standard automatique ou file d’attente d’appels. Les comptes de ressources peuvent également se voir attribuer des numéros de téléphone de service. C’est ainsi que vous attribuez des numéros de téléphone aux standards automatiques et aux files d’attente d’appels, ce qui permet aux appelants extérieurs à Teams d’atteindre le standard automatique ou la file d’attente d’appels.

Cet article explique comment créer des comptes de ressources et les préparer pour une utilisation avec des standards automatiques et des files d’attente d’appels.

Avant de commencer les procédures décrites dans cet article, vérifiez que vous avez effectué les opérations suivantes :

- [Obtenir des licences de compte de ressource Téléphonie Microsoft Teams](#obtain-microsoft-teams-phone-resource-account-licenses)
- [Obtenir des numéros de service](#obtain-service-numbers)

> [!NOTE]
> Les comptes de ressources utilisés pour les standards automatiques et les files d’attente d’appels sont désactivés pour la connexion et doivent le rester. La conversation et la présence ne sont pas disponibles pour ces comptes.

### <a name="obtain-microsoft-teams-phone-resource-account-licenses"></a>Obtenir des licences de compte de ressource Téléphonie Microsoft Teams

Chaque compte de ressource nécessite une licence pour fonctionner avec les standards automatiques et les files d’attente d’appels. Vous pouvez utiliser une licence *de compte de ressource Téléphonie Microsoft Teams* gratuite. Pour obtenir ces licences, consultez [Téléphonie Microsoft Teams licences de compte de ressources](../teams-add-on-licensing/virtual-user.md).

Nous aborderons [la façon d’attribuer la licence à un compte de ressource plus loin dans cet article](#assign-a-license).

Si vous avez acheté **des** licences Téléphonie Teams standard ou **Teams Phone avec forfait d’appels** groupés, les licences *de compte de ressources de téléphone Teams* se trouvent déjà dans votre compte.

Pour voir si vous disposez déjà de licences de compte de ressources, connectez-vous à Microsoft 365 à l’aide d’un compte disposant d’autorisations d’administrateur général. Ensuite, accédez à [Facturation > vos produits](https://admin.microsoft.com/Adminportal/Home#/subscriptions). Si vous disposez de licences de compte de ressources, elles apparaissent comme **Téléphonie Microsoft Teams compte de ressources**.

1. Ouvrez le Centre d'administration Microsoft 365 et connectez-vous avec un utilisateur administrateur général. Il s’agit généralement du compte que vous avez utilisé pour vous inscrire à Microsoft 365.
2. Dans le volet de navigation gauche, [**accédez** **aux** >  modules](https://admin.microsoft.com/Adminportal/Home#/catalog)**complémentaires** >  Billing Purchase Services  > **Voir tous les produits de modules complémentaires**.
3. Faites défiler jusqu’à la fin pour rechercher la **licence Téléphonie Microsoft Teams compte de ressource**. Sélectionnez **Détails**, puis **Achetez**.
4. Dans la page d’achat de licences, sélectionnez le nombre de licences de compte de ressources souhaitées. Vous avez besoin d’une licence de compte de ressource pour chaque standard automatique et file d’attente d’appels que vous prévoyez de configurer. Nous vous recommandons de sélectionner au moins cinq licences afin que vous puissiez facilement configurer plus de standards automatiques et appeler des files d’attente à l’avenir sans avoir à acheter plus de licences immédiatement.
5. Désactivez **automatiquement l’affectation à tous vos utilisateurs sans licence**.
6. **Sélectionnez Extraire maintenant**.
7. Confirmez votre commande, sélectionnez **Suivant**, puis **Passez commande**.

Il n’y a aucun coût, mais vous devez toujours suivre ces étapes pour acquérir la licence.

### <a name="obtain-service-numbers"></a>Obtenir des numéros de service

Les numéros de service sont facultatifs pour les standards automatiques et les files d’attente d’appels, mais vous aurez besoin d’au moins un numéro de service pour que les appelants atteignent votre standard automatique et la configuration de la file d’attente d’appels. Pour tout standard automatique ou file d’attente d’appels que vous souhaitez atteindre directement par un numéro de service, vous devez disposer d’un compte de ressource avec un numéro de service associé.

Les comptes de ressources peuvent utiliser des numéros de service payants ou gratuits. Vous pouvez demander de nouveaux numéros ou porter des numéros existants auprès d’un autre opérateur.

Pour obtenir de nouveaux numéros de service, consultez [Obtenir les numéros de téléphone du service](../getting-service-phone-numbers.md).

Pour porter un numéro à partir d’un autre opérateur, consultez [Transférer des numéros de téléphone vers Teams](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md).

## <a name="create-a-resource-account"></a>Créer un compte de ressource

Vous pouvez créer un compte de ressource dans le Centre d’administration Teams.

1. Dans le Centre d’administration Teams, développez **Voix**, puis sélectionnez **Comptes de ressources**.
2. Sélectionnez **Ajouter**.
3. Dans le volet **Ajouter un compte de ressource** , **renseignez le nom d’affichage**, le **nom d’utilisateur** et le **type de compte de ressource**. Le type de compte de ressource peut être standard **automatique** ou **file d’attente d’appels**, selon la façon dont vous envisagez d’utiliser ce compte de ressource.
4. Sélectionnez **Enregistrer**.

## <a name="assign-a-license"></a>Attribuer une licence

Pour chaque compte de ressource, vous devez attribuer une licence *de compte* de ressource Téléphonie Microsoft Teams ou *une licence Téléphonie Teams standard*.

1. Dans le Centre d'administration Microsoft 365, développez **Utilisateurs**, puis sélectionnez **Utilisateurs actifs**.
2. Sélectionnez le compte de ressource auquel vous souhaitez attribuer une licence. Le volet utilisateur du compte de ressource s’affiche.
3. Sous l’onglet **Licences et applications**, sous **Licences**, sélectionnez **Téléphonie Microsoft Teams Compte de ressources**.
4. Sélectionnez **Enregistrer les modifications**.

## <a name="assign-a-service-number"></a>Attribuer un numéro de service

Si vous envisagez d’utiliser le compte de ressource avec un standard automatique ou une file d’attente d’appels nécessitant un numéro de service, attribuez un numéro au compte de ressource.

1. Dans le Centre d’administration Teams, dans la page **Comptes de** ressources, sélectionnez le compte de ressource auquel vous souhaitez attribuer un numéro de service, puis **sélectionnez Affecter/annuler l’affectation**.
2. Dans la liste déroulante **Type de numéro de téléphone** , choisissez le type de numéro que vous souhaitez utiliser.
3. Dans la zone **Numéro de téléphone affecté** , recherchez le numéro que vous souhaitez utiliser, puis sélectionnez **Ajouter**. Veillez à inclure le code de pays (par exemple, +1 250 555 0012).
4. Sélectionnez **Enregistrer**.

Pour affecter un routage direct ou un numéro hybride à un compte de ressource, vous devez utiliser PowerShell :

`Set-CsPhoneNumberAssignment -Identity aa-contoso_main@contoso64.net -PhoneNumber +19295550150 -PhoneNumberType DirectRouting`