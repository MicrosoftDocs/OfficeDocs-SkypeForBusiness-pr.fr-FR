---
title: Configurer un contrôleur de frontière de session pour plusieurs clients
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
appliesto: Microsoft Teams
description: Découvrez comment configurer un contrôleur de Session bordure (SBC) pour prendre en charge plusieurs clients.
ms.openlocfilehash: 53cc4d6f9d930c9069ac39d81e304b0265669b5e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30893342"
---
# <a name="configure-a-session-border-controller-for-multiple-tenants"></a>Configurer un contrôleur de frontière de session pour plusieurs clients

Routage direct prend en charge la configuration une bordure contrôleur Session (SBC) pour prendre en charge plusieurs clients.

> [!NOTE]
> Ce scénario est conçu pour les partenaires Microsoft et/ou des opérateurs PSTN, appelés opérateurs plus loin dans ce document. Un opérateur vend remis à Microsoft Teams à leurs clients des services de téléphonie. 

Un opérateur :
- Déploie et gère un contrôleur SBC dans leur centre de données (clients n’avez pas besoin d’implémenter un contrôleur SBC, et ils reçoivent des services de téléphonie de l’opérateur dans le client équipes).
- Relie le contrôleur SBC à plusieurs clients.
- Fournit des services PSTN pour les clients.
- Gère la qualité des appels bout en bout.
- Frais séparément de services PSTN.

Microsoft ne gère pas les opérateurs. Microsoft offre un système PBX (système téléphonique de Microsoft) et un client équipes, atteste de téléphones et atteste SBCs qui peuvent être utilisés avec le système téléphonique de Microsoft. Avant de choisir un opérateur, assurez-vous que votre choix a une SBC certifié et peut gérer la qualité de voix bout en bout.

Voici les étapes de mise en œuvre technique pour configurer le scénario.

**Opérateur :**
1. Déployer le contrôleur SBC et le configurer pour le scénario d’hébergement conformément aux [instructions des fournisseurs SBC certifiés](#deploy-and-configure-the-sbc).
2. Enregistrer un nom de domaine de base dans le client de l’opérateur et demander un certificat générique.
3. Inscrire un sous-domaine pour chaque client qui fait partie du domaine de base.

**Support administrateur Global client :**
1. Ajouter le nom du sous-domaine au client client.
2. Activer le nom du sous-domaine.
3. Configurer la jonction de l’opérateur pour les utilisateurs de client et de mise en service du client.

*Assurez-vous que vous comprenez les concepts de base DNS et comment le nom de domaine est géré dans Office 365. Avant de continuer, consultez [obtenir de l’aide avec les domaines d’Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) .*

## <a name="deploy-and-configure-the-sbc"></a>Déployer et configurer le contrôleur SBC

Pour obtenir les étapes détaillées sur la façon de déployer et configurer SBC pour un scénario d’hébergement SBC, reportez-vous à la documentation de SBC.

- **AudioCodes :** [Notes de Configuration de routage direct](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams), la configuration de la SBC hébergeant le scénario décrit dans « Connexion AudioCodes SBC à Microsoft Teams Direct routage hébergement modèle Configuration Note ». 
- **Communications de ruban :**  Reportez-vous au [Guide de Configuration du ruban Communications SBC principaux Microsoft équipes](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe) pour la documentation sur la configuration du ruban principal série SBCs et à cette page [conseillée ruban - configuration d’opérateurs de SBC de routage Direct Microsoft équipes Edge](https://support.sonus.net/display/UXDOC70/Best+Practice+-+Configuring+Carriers+for+Microsoft+Teams+Direct+Routing)

> [!NOTE]
> Prêtez attention à la configuration de l’en-tête « Contacts ». L’en-tête de Contact est utilisé pour trouver le client du client sur le message invite entrant. 

## <a name="register-a-base-domain-and-subdomains"></a>Inscrire un domaine de base et les sous-domaines

Pour le scénario d’hébergement, vous devez créer :
- Un nom de domaine de base détenu par l’opérateur.
- Un sous-domaine qui fait partie du nom de domaine de base dans chaque client du client.

Dans l’exemple suivant :
- Adatum est un opérateur qui sert de plusieurs clients en fournissant des services Internet et de téléphonie.
- Woodgrove Bank, Contoso et Adventure Works les trois clients qui ont des domaines d’Office 365, mais les services de téléphonie des Adatum.

Sous-domaines **doit** correspondent au nom de nom de domaine complet de la jonction qui vont être configuré pour le client et le nom de domaine complet dans l’en-tête de Contact lors de l’envoi de l’invitation à Office 365. 

Lorsqu’un appel arrive à l’interface de routage Direct Office 365, l’interface utilise l’en-tête de Contact pour trouver le client où l’utilisateur doit être recherché. Routage direct n’utilise pas recherche de numéros de téléphone dans l’invitation, comme certains clients peut-être non-avez-vous numéros peuvent se chevaucher dans plusieurs clients. Par conséquent, le nom de domaine complet dans l’en-tête de Contact est requis pour identifier le client exact pour rechercher l’utilisateur par le numéro de téléphone.

*Consultez [obtenir de l’aide avec les domaines d’Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) pour plus d’informations sur la création des noms de domaine dans les clients Office 365.*

Le diagramme suivant résume la configuration requise pour l’en-tête de Contact, sous-domaines et le domaine de base.

![Conditions requises pour l’en-tête de Contact, sous-domaines et le domaine de base](media/direct-routing-1-sbc-requirements.png)

Le contrôleur SBC nécessite un certificat pour authentifier les connexions. Pour le scénario d’hébergement SBC, l’opérateur doit demander un certificat avec SAN * \*.base_domain (par exemple, \*customers.adatum.biz)*. Ce certificat peut être utilisé pour authentifier des connexions à plusieurs locataires traitées à partir d’un contrôleur SBC unique.

Le tableau suivant est un exemple d’une configuration.


|Nouveau nom de domaine |Type|Inscrit  |Certificat SAN pour SBC  |Domaine par défaut de client dans l’exemple  |Nom de domaine complet SBC doit présenter dans l’en-tête de Contact lors de l’envoi des appels aux utilisateurs|
|---------|---------|---------|---------|---------|---------|
|Customers.adatum.biz|    Base de     |     Dans le client de l’opérateur  |    \*. customers.adatum.biz  |   adatum.biz      |NA, il s’agit d’un client de service, pas d’utilisateurs |
|sbc1.Customers.adatum.biz|    Sous-domaine  |    Dans un client de client  |    \*. customers.adatum.biz  | woodgrovebank.us  |  sbc1.Customers.adatum.biz|
|sbc2.Customers.adatum.biz  |   Sous-domaine | Dans un client de client   |   \*. customers.adatum.biz   |contoso.com   |sbc2.Customers.adatum.biz |
|SBC3.Customers.adatum.biz |   Sous-domaine | Dans un client de client |   \*. customers.adatum.biz  |  AdventureWorks.com | SBC3.Customers.adatum.biz |
||         |         |         |         |         |

Pour configurer la base et les sous-domaines, suivez les étapes décrites ci-dessous. Dans l’exemple, nous allons configurer un nom de domaine de base (customers.adatum.biz) et un sous-domaine d’un seul client (sbc1.customers.adatum.biz dans client Woodgrove Bank).

## <a name="register-a-base-domain-name-in-the-carrier-tenant"></a>Enregistrer un nom de domaine de base dans le client de l’opérateur

**Ces actions sont effectuées dans le client de l’opérateur.**

### <a name="ensure-that-you-have-appropriate-rights-in-the-carrier-tenant"></a>Vérifiez que vous disposez des droits appropriés dans le client de l’opérateur

Vous pouvez ajouter de nouveaux domaines uniquement si vous vous êtes le centre d’administration Office 365 en tant qu’administrateur Global. 

Pour valider le rôle que vous avez, connectez-vous au centre d’administration Microsoft 365 (https://portal.office.com), accédez aux **utilisateurs** > **Utilisateurs actifs**, puis vérifiez que vous disposez d’un rôle Administrateur général. 

Pour plus d’informations sur les rôles d’administrateur et comment affecter un rôle dans Office 365, voir [rôles d’administrateur sur Office 365](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).

### <a name="add-a-base-domain-to-the-tenant-and-verify-it"></a>Ajouter un domaine de base au client et vérifiez qu’il

1.  Dans le centre d’administration Microsoft 365, accédez à **configuration** > **domaines** > **Ajouter domaine**.
2.  Dans la zone **Entrez un domaine que vous êtes propriétaire** , tapez le nom de domaine complet du domaine de base. Dans l’exemple suivant, le domaine de base est *customers.adatum.biz*.

    ![Ajout d’un domaine de base](media/direct-routing-2-sbc-add-domain.png)

3. Cliquez sur **Suivant**.
4. Dans l’exemple, le client a déjà adatum.biz sous un nom de domaine vérifié. L’Assistant vous demandera pas une vérification supplémentaire, car customers.adatum.biz est un sous-domaine du nom déjà enregistrée. Toutefois, si vous ajoutez un nom de domaine qui n’a pas été vérifié, vous devez suivre le processus de vérification. Le processus de vérification est [décrit ci-dessous](#add-a-subdomain-to-the-customer-tenant-and-verify-it).

    ![Confirmation d’un nom de domaine vérifié](media/direct-routing-3-sbc-verify-domain.png)

5.  Cliquez sur **suivant**et dans la page **Paramètres de mise à jour DNS** , sélectionnez **je vais ajouter les enregistrements DNS moi-même** et cliquez sur **suivant**.
6.  Dans la page suivante, désactivez toutes les valeurs (sauf si vous souhaitez utiliser le nom de domaine pour Exchange, SharePoint ou équipes/Skype pour les entreprises), cliquez sur **suivant**, puis cliquez sur **Terminer**. Assurez-vous que votre nouveau domaine se trouve dans l’état complet du programme d’installation.

    ![Domaines indiquant l’état d’installation complète](media/direct-routing-14-sbc-setup-complete.png)

### <a name="activate-the-domain-name"></a>Activer le nom de domaine

Une fois que vous avez enregistré un nom de domaine, vous devez l’activer en ajoutant au moins un E1, E3, ou E5 sous licence utilisateur et attribution d’une adresse SIP avec la partie nom de domaine complet du SIP d’adresse correspondant à ce domaine de base créé. 

*Consultez [obtenir de l’aide avec les domaines d’Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) pour plus d’informations sur l’ajout d’utilisateurs dans les clients Office 365.*

Par exemple : test@customers.adatum.biz

![Page d’activation du domaine de base](media/direct-routing-4-sbc-domain-activation.png)

## <a name="register-a-subdomain-name-in-a-customer-tenant"></a>Inscrire un nom de sous-domaine dans un client de client

Vous devez créer un nom de sous-domaine unique pour chaque client. Dans cet exemple, nous allons créer un sous-domaine sbc1.customers.adatum.biz dans un client avec le woodgrovebank.us de nom de domaine par défaut.

**Toutes les actions ci-dessous sont dans le client du client.**

### <a name="ensure-that-you-have-appropriate-rights-in-the-customer-tenant"></a>Vérifiez que vous disposez des droits appropriés dans le client du client

Vous pouvez ajouter de nouveaux domaines uniquement si vous vous êtes le centre d’administration Office 365 en tant qu’administrateur Global. 

Pour valider le rôle que vous avez, connectez-vous au centre d’administration Microsoft 365 (https://portal.office.com), accédez aux **utilisateurs** > **Utilisateurs actifs**, puis vérifiez que vous disposez d’un rôle Administrateur général. 

Pour plus d’informations sur les rôles d’administrateur et comment affecter un rôle dans Office 365, voir [rôles d’administrateur sur Office 365](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).

### <a name="add-a-subdomain-to-the-customer-tenant-and-verify-it"></a>Ajouter un sous-domaine au client client et vérifiez qu’il
1. Dans le centre d’administration Microsoft 365, accédez à **configuration** > **domaines** > **Ajouter domaine**.
2. Dans la zone **Entrez un domaine que vous êtes propriétaire** , tapez le nom de domaine complet du sous-domaine pour ce client. Dans l’exemple ci-dessous, le sous-domaine est sbc1.customers.adatum.biz.

    ![Ajout d’un sous-domaine du client](media/direct-routing-5-sbc-add-customer-domain.png)

3. Cliquez sur **Suivant**.
4. Le nom de domaine complet n’a jamais été enregistré dans le client. Dans l’étape suivante, vous devez vérifier le domaine. Sélectionnez **Ajouter un enregistrement TXT à la place**. 

    ![Options de la page vérifier le domaine](media/direct-routing-6-sbc-verify-customer-domain.png)

5. Cliquez sur **suivant**et notez la valeur TXT générée pour vérifier le nom de domaine.

    ![Enregistrements de texte sur la page vérifier le domaine](media/direct-routing-7-sbc-verify-domain-txt.png)

6. Créer l’enregistrement TXT avec la valeur de l’étape précédente dans le fournisseur d’hébergement DNS de l’opérateur mobile.

    ![Création de l’enregistrement TXT dans le fournisseur d’hébergement DNS de l’opérateur](media/direct-routing-8-sbc-txt-record.png)

    Pour plus d’informations, reportez-vous à [créer des enregistrements DNS à n’importe quel fournisseur d’hébergement DNS pour Office 365](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166).

7. Revenez au centre d’administration de Microsoft 365 du client et cliquez sur **Vérifier**. 
8. Dans la page suivante, sélectionnez **je vais ajouter les enregistrements DNS moi-même** , puis cliquez sur **suivant**.

    ![Options de la page Paramètres de mise à jour DNS](media/direct-routing-9-sbc-update-dns.png)

9. Dans la page **Choisir vos services en ligne** , désactivez toutes les options, cliquez sur **suivant**.

    ![La choisir votre page services en ligne](media/direct-routing-10-sbc-choose-services.png)

10. Dans la page **paramètres de mise à jour DNS** , cliquez sur **Terminer** .

    ![La page Paramètres de mise à jour DNS](media/direct-routing-11-sbc-update-dns-finish.png)

11. Assurez-vous que l’état est **de terminer l’installation**. 
    
    ![Page indiquant l’état du programme d’installation complète](media/direct-routing-12-sbc-setup-complete.png)

### <a name="activate-the-subdomain-name"></a>Activer le nom du sous-domaine

Après avoir inscrit un nom de domaine, vous devez l’activer en ajoutant au moins un utilisateur et attribuer une adresse SIP avec la partie nom de domaine complet de l’adresse SIP correspondant le sous-domaine créé dans le client du client.

*Consultez [obtenir de l’aide avec les domaines d’Office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) pour plus d’informations sur l’ajout d’utilisateurs dans les clients Office 365.*

Par exemple : test@sbc1.customers.adatum.biz

![Activation de la page sous-domaine](media/direct-routing-13-sbc-activate-subdomain.png)

### <a name="create-a-trunk-and-provision-users"></a>Créer une jonction et la mise en service des utilisateurs

> [!NOTE]
> En fonction des commentaires reçus dans le programme d’Adoption technique, Microsoft peut changer le processus de création de jonctions dans les clients de client pour simplifier le processus. Veuillez regarder les mises à jour de la documentation sur cette page et suivez les blogs de la Communauté technique Microsoft pour plus d’informations. 

Créer une jonction dans le domaine de client à l’aide de la commande New-CSonlinePSTNGateway. La jonction de nom de domaine complet **doit** correspondre le sous-domaine créé pour le client.

Par exemple :

```
New-CSOnlinePSTNGateway –FQDN sbc1.customers.adatum.biz -SipSignallingPort 5068
```

Lorsque vous créez la jonction, le message d’erreur suivant s’affiche :

```
Can not use the "sbc1.customers.adatum.biz" domain as it was not configured for this tenant.
```

Prévoyez un peu de temps pour l’enregistrement du domaine et d’activation à répliquer, puis réessayez.

Configurer les utilisateurs avec les numéros de téléphone et configurer le routage des communications vocales.

Pour plus d’informations sur le nouveau-CSOnlinePSTNGateway, mise en service des utilisateurs et la configuration de routage des communications vocales, reportez-vous à [Configurer le routage Direct](direct-routing-configure.md).


Consultez les [instructions du fournisseur SBC](#deploy-and-configure-the-sbc) sur la configuration de l’envoi du nom de domaine complet des sous-domaines dans l’en-tête du Contact.

