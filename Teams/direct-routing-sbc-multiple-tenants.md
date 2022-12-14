---
title: Configurer le contrôleur de bordure de session - Plusieurs locataires
ms.reviewer: filippse
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Découvrez comment configurer un contrôleur de bordure de session (SBC) pour servir plusieurs locataires pour des partenaires Microsoft et/ou des opérateurs RTC.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 570709730f7563b30b98626395f6b0a72fc1ac48
ms.sourcegitcommit: 0d97dc6616b3d633564409e39c08311af1522705
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/14/2022
ms.locfileid: "69392294"
---
# <a name="configure-a-session-border-controller-for-multiple-tenants"></a>Configurer un contrôleur de frontière de session pour plusieurs clients

Le routage direct prend en charge la configuration d’un contrôleur de bordure de session (SBC) pour servir plusieurs locataires.

> [!NOTE]
> Ce scénario est conçu pour Microsoft partenaires et/ou opérateurs RTC, appelés opérateurs plus loin dans ce document. Un opérateur vend des services de téléphonie fournis à Microsoft Teams à ses clients. 

Un opérateur :
- Déploie et gère un SBC dans leur centre de données (les clients n’ont pas besoin d’implémenter un SBC et reçoivent des services de téléphonie de l’opérateur dans le client Teams).
- Interconnecte le SBC à plusieurs locataires.
- Fournit des services de réseau téléphonique commuté public (RTC) aux clients.
- Gère la qualité des appels de bout en bout.
- Les frais sont facturés séparément pour les services RTC.

Microsoft ne gère pas les opérateurs. Microsoft offre un système téléphonique (PBX) et un client Teams. Microsoft certifie également les téléphones et certifie les SBC qui peuvent être utilisés avec le système téléphonique. Avant de choisir un opérateur, assurez-vous que votre choix dispose d’un SBC certifié et peut gérer la qualité de la voix de bout en bout.

Voici les étapes d’implémentation technique pour configurer le scénario.

**Opérateur uniquement :**
1. Déployez le SBC et configurez-le pour le scénario d’hébergement en suivant [les instructions des fournisseurs SBC certifiés](#deploy-and-configure-the-sbc).
2. Inscrivez un nom de domaine de base dans le locataire de l’opérateur et demandez un certificat générique.
3. Inscrivez un sous-domaine pour chaque client, qui fait partie du domaine de base.

**Opérateur avec un administrateur général client :**
1. Ajoutez le nom du sous-domaine au locataire du client.
2. Activez le nom du sous-domaine.
3. Configurez la jonction entre l’opérateur et le locataire client et provisionnez les utilisateurs.

*Assurez-vous de bien comprendre les principes de base du DNS et la façon dont le nom de domaine est géré dans Microsoft 365. Consultez [Obtenir de l’aide sur Microsoft 365 domaines](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) avant de poursuivre.*

## <a name="deploy-and-configure-the-sbc"></a>Déployer et configurer le SBC

Pour obtenir des instructions détaillées sur le déploiement et la configuration des SBC pour un scénario d’hébergement SBC, consultez la documentation du fournisseur SBC.

- **AudioCodes :** Consultez [les notes de configuration du routage direct](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams) pour la configuration du scénario d’hébergement SBC, comme décrit dans « Connexion d’AudioCodes SBC à Microsoft Teams Direct Routing Hosting Model Note ». 
- **Oracle:** Consultez [les notes sur la configuration du routage direct](https://www.oracle.com/technetwork/indexes/documentation/acme-packet-2228107.html) pour la configuration du scénario d’hébergement SBC, comme décrit dans la section « Microsoft ». 
- **Communications du ruban :** Pour obtenir de la documentation sur la configuration des [SBC Série SBC Core Microsoft Teams, consultez Ribbon Communications SBC Core](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+MS+Teams+Solution+Guide). Voir aussi [Meilleures pratiques du ruban - Configuration des opérateurs pour Microsoft Teams Direct Routing SBC Edge](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Direct+Routing+Carrier)
- **TE-Systems (anynode) :** Inscrivez-vous sur le site de la [page communauté TE-Systems](https://community.te-systems.de/) pour obtenir de la documentation et des exemples sur la configuration d’anynode SBC pour plusieurs locataires.
- **Metaswitch :** Inscrivez-vous sur le site de [la page Communauté Metaswitch](https://manuals.metaswitch.com/MAN39555) pour obtenir de la documentation sur l’activation de Perimeta SBC pour plusieurs locataires.

> [!NOTE]
> Vérifiez que vous savez comment configurer l’en-tête « Contact ». L’en-tête Contact est utilisé pour rechercher le locataire du client sur le message d’invitation entrant. 

## <a name="register-a-base-domain-and-subdomains"></a>Inscrire un domaine de base et des sous-domaines

Pour le scénario d’hébergement, vous devez créer :

- Un nom de domaine de base appartenant à l’opérateur.
- Sous-domaine qui fait partie du nom de domaine de base dans chaque locataire client.

Dans l’exemple suivant :

- Adatum est un opérateur qui dessert plusieurs clients en fournissant des services Internet et de téléphonie.
- Woodgrove Bank, Contoso et Adventure Works sont trois clients qui ont Microsoft 365 domaines, mais qui reçoivent les services de téléphonie d’Adatum.

Les sous-domaines **DOIVENT** correspondre au nom de domaine complet de la jonction qui sera configurée pour le client et au nom de domaine complet dans l’en-tête Contact lors de l’envoi de l’invitation à Microsoft 365. 

Lorsqu’un appel arrive à l’interface de routage direct Microsoft 365, l’interface utilise l’en-tête Contact pour rechercher le locataire dans lequel l’utilisateur doit être recherché. Le routage direct n’utilise pas la recherche de numéro de téléphone sur l’invite, car certains clients peuvent avoir des numéros non DID qui peuvent se chevaucher dans plusieurs locataires. Par conséquent, le nom de domaine complet dans l’en-tête Contact est requis pour identifier le locataire exact pour rechercher l’utilisateur par le numéro de téléphone.

*Pour plus d’informations sur la création de noms de domaine dans Microsoft 365 organisations, consultez [Obtenir de l’aide sur Microsoft 365 domaines](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).*

Le diagramme suivant résume la configuration requise pour le domaine de base, les sous-domaines et l’en-tête Contact.

:::image type="content" source="media/direct-routing-1-sbc-requirements.png" alt-text="Diagramme montrant les conditions requises pour les domaines et l’en-tête contact." lightbox="media/direct-routing-1-sbc-requirements.png":::

Le SBC nécessite un certificat pour authentifier les connexions. Pour le scénario d’hébergement SBC, l’opérateur doit demander un certificat avec cn et/ou SAN *\*.base_domain (par exemple, \*.customers.adatum.biz).* Ce certificat peut être utilisé pour authentifier les connexions à plusieurs locataires servis à partir d’un même SBC.

Le tableau suivant est un exemple d’une configuration.


|Nouveau nom de domaine |Type|Enregistré  |Cn/SAN de certificat pour SBC  |Domaine par défaut du locataire dans l’exemple  |Nom de domaine complet que SBC doit présenter dans l’en-tête Contact lors de l’envoi d’appels aux utilisateurs|
|---------|---------|---------|---------|---------|---------|
|customers.adatum.biz|    Base     |     Dans le locataire de l’opérateur  |    \*.customers.adatum.biz  |   adatum.biz      |NA, il s’agit d’un locataire de service, aucun utilisateur |
|sbc1.customers.adatum.biz|    Sous-domaine  |    Dans un locataire client  |    \*.customers.adatum.biz  | woodgrovebank.us  |  sbc1.customers.adatum.biz|
|sbc2.customers.adatum.biz  |   Sous-domaine | Dans un locataire client   |   \*.customers.adatum.biz   |contoso.com   |sbc2.customers.adatum.biz |
|sbc3.customers.adatum.biz |   Sous-domaine | Dans un locataire client |   \*.customers.adatum.biz  |  adventureworks.com | sbc3.customers.adatum.biz |

Pour configurer la base et les sous-domaines, suivez les étapes décrites ci-dessous. Cet exemple configure un nom de domaine de base (customers.adatum.biz) et un sous-domaine pour un client (sbc1.customers.adatum.biz dans le locataire Woodgrove Bank).

> [!NOTE]
> Utilisez sbcX.customers.adatum.biz pour activer la voix dans le locataire de l’opérateur ; sbcX peut être n’importe quel nom d’hôte alphanumérique unique et valide.

## <a name="register-a-base-domain-name-in-the-carrier-tenant"></a>Inscrire un nom de domaine de base dans le locataire de l’opérateur

**Ces actions sont effectuées dans le locataire de l’opérateur.**

### <a name="ensure-that-you-have-appropriate-rights-in-the-carrier-tenant"></a>Vérifiez que vous disposez des droits appropriés dans le locataire de l’opérateur

Vous ne pouvez ajouter de nouveaux domaines que si vous vous êtes connecté au Centre d'administration Microsoft 365 en tant qu’administrateur général. 

Pour valider le rôle dont vous disposez, connectez-vous à la Centre d'administration Microsoft 365 (https://portal.office.com), accédez à **Utilisateurs** > **utilisateurs actifs**, puis vérifiez que vous disposez d’un rôle Administrateur général. 

Pour plus d’informations sur les rôles d’administrateur et sur l’attribution d’un rôle dans Microsoft 365, consultez [À propos des rôles d’administrateur](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).

### <a name="add-a-base-domain-to-the-tenant-and-verify-it"></a>Ajouter un domaine de base au locataire et le vérifier

1. Dans le Centre d'administration Microsoft 365, accédez à **Configurer les** > **domaines** > **Ajouter un domaine**.

2. Dans la zone **Entrer un domaine que vous possédez** , tapez le nom de domaine complet du domaine de base. Dans l’exemple suivant, le domaine de base est *customers.adatum.biz*.

3. Cliquez sur **Suivant**.

4. Dans cet exemple, le locataire a déjà adatum.biz en tant que nom de domaine vérifié. L’Assistant ne demande pas de vérification supplémentaire, car customers.adatum.biz est un sous-domaine pour le nom déjà inscrit. Toutefois, si vous ajoutez un nom de domaine complet qui n’a pas été vérifié auparavant, vous devez suivre le processus de vérification. Le processus de vérification est [décrit ci-dessous](#add-a-subdomain-to-the-customer-tenant-and-verify-it).

5. Sélectionnez **Suivant**, puis, dans la page **Mettre à jour les paramètres DNS** , sélectionnez **J’ajouterai les enregistrements DNS moi-même** , puis sélectionnez **Suivant**.

6. Dans la page suivante, effacez toutes les valeurs (sauf si vous souhaitez utiliser le nom de domaine pour Exchange, SharePoint, Teams ou Skype Entreprise), sélectionnez **Suivant**, puis **Terminer**. Vérifiez que votre nouveau domaine est dans l’état Complet de l’installation.

### <a name="activate-the-domain-name"></a>Activer le nom de domaine

Une fois que vous avez inscrit un nom de domaine, vous devez l’activer en ajoutant au moins un compte d’utilisateur ou de ressource sous licence Teams. Les comptes acceptables seront concédés sous licence avec l’une des références SKU suivantes :

- Compte d’utilisateur avec Office 365 E1/E3/E5 ou Microsoft 365 E3/E5.
- Compte d’utilisateur avec Office 365 A1/A3/A5 ou Microsoft 365 A1/A3/A5.
- Compte d’utilisateur avec Office 365 F3 ou Microsoft 365 F1/F3.
- Compte d’utilisateur avec Office 365 G1/G3/G5 ou Microsoft 365 G3/G5.
- Compte d’utilisateur avec Microsoft 365 Business Basic/Standard/Premium.
- Compte d’utilisateur avec une licence **d’appareils partagés Microsoft Teams**.
- Compte de ressource avec une licence **de compte de ressource Téléphonie Microsoft Teams**.

En outre, l’UPN (Nom d’utilisateur principal) ou Skype Entreprise adresse SIP locale du compte doit utiliser le même nom de domaine complet que le domaine nouvellement créé.

Pour plus d’informations sur l’ajout d’utilisateurs dans Microsoft 365 organisations, consultez [Obtenir de l’aide sur Microsoft 365 domaines](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).

Par exemple : test@customers.adatum.biz

![Capture d’écran de la page d’activation du domaine de base.](media/direct-routing-4-sbc-domain-activation.png)

## <a name="register-a-subdomain-name-in-a-customer-tenant"></a>Inscrire un nom de sous-domaine dans un locataire client

Vous devez créer un nom de sous-domaine unique pour chaque client. Dans cet exemple, nous allons créer un sous-domaine sbc1.customers.adatum.biz dans un locataire avec le nom de domaine par défaut woodgrovebank.us.

**Toutes les actions ci-dessous se trouvent dans le locataire du client.**

### <a name="ensure-that-you-have-appropriate-rights-in-the-customer-tenant"></a>Vérifiez que vous disposez des droits appropriés dans le locataire du client

Vous ne pouvez ajouter de nouveaux domaines que si vous vous êtes connecté au Centre d'administration Microsoft 365 en tant qu’administrateur général. 

Pour valider le rôle dont vous disposez, connectez-vous à la Centre d'administration Microsoft 365 (https://portal.office.com), accédez à **Utilisateurs** > **utilisateurs actifs**, puis vérifiez que vous disposez d’un rôle Administrateur général. 

Pour plus d’informations sur les rôles d’administrateur et sur l’attribution d’un rôle dans Microsoft 365, consultez [À propos des rôles d’administrateur](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).

### <a name="add-a-subdomain-to-the-customer-tenant-and-verify-it"></a>Ajouter un sous-domaine au locataire du client et le vérifier

1. Dans le Centre d'administration Microsoft 365, accédez à **Configurer les** > **domaines** > **Ajouter un domaine**.

2. Dans la zone **Entrer un domaine que vous possédez** , tapez le nom de domaine complet du sous-domaine pour ce locataire. Dans l’exemple ci-dessous, le sous-domaine est sbc1.customers.adatum.biz.

3. Sélectionnez **Suivant**.

4. Le nom de domaine complet n’a jamais été inscrit dans le locataire. À l’étape suivante, vous devez vérifier le domaine. Sélectionnez **Plutôt Ajouter un enregistrement TXT**. 

5. Sélectionnez **Suivant**, puis notez la valeur TXT générée pour vérifier le nom de domaine.

    ![Capture d’écran des enregistrements texte sur la page Vérifier le domaine.](media/direct-routing-7-sbc-verify-domain-txt.png)

6. Créez l’enregistrement TXT avec la valeur de l’étape précédente dans le fournisseur d’hébergement DNS de l’opérateur.

    Pour plus d’informations, consultez [Créer des enregistrements DNS sur n’importe quel fournisseur d’hébergement DNS](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166).

7. Accédez à la Centre d'administration Microsoft 365 du client, puis sélectionnez **Vérifier**. 

8. Sur la page suivante, sélectionnez **Je vais ajouter les enregistrements DNS moi-même** , puis sélectionnez **Suivant**.

9. Dans la page **Choisir votre services en ligne**, désactivez toutes les options et sélectionnez **Suivant**.

10. Sélectionnez **Terminer** dans la page **Mettre à jour les paramètres DNS** .

11. Vérifiez que l’état est **l’installation terminée**.

    ![Capture d’écran de la page montrant l’état de l’installation terminée.](media/direct-routing-12-sbc-setup-complete.png)

> [!NOTE]
> L’URL de base et le sous-domaine du client individuel doivent se trouver sur le même locataire pour vous permettre d’ajouter une _jonction de routage directe_ .

### <a name="activate-the-subdomain-name"></a>Activer le nom du sous-domaine

Une fois que vous avez inscrit un nom de sous-domaine, vous devez l’activer en ajoutant au moins un compte d’utilisateur ou de ressource sous licence Teams. Les comptes acceptables seront concédés sous licence avec l’une des références SKU suivantes :

-   Compte d’utilisateur avec Office 365 E1/E3/E5/A3/A5 ou Microsoft 365 E3/E5/A3/A5
-   Compte d’utilisateur avec Office 365 F1/F3 ou Microsoft 365 F1/F3
-   Compte d’utilisateur avec des plans Microsoft 365 Business Basic/Standard/Premium et G3/G5
-   Compte d’utilisateur avec une licence **d’appareils partagés Microsoft Teams**
-   Compte de ressource avec une licence **de compte de ressource Téléphonie Microsoft Teams**

En outre, l’UPN (Nom d’utilisateur principal) ou l’adresse SIP Skype Entreprise locale du compte doit utiliser le même nom de domaine complet que le sous-domaine nouvellement créé.

Pour plus d’informations sur l’ajout d’utilisateurs dans Microsoft 365 organisations, consultez [Obtenir de l’aide sur Microsoft 365](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).

Par exemple : test@sbc1.customers.adatum.biz

![Capture d’écran de la page Activation du sous-domaine.](media/direct-routing-13-sbc-activate-subdomain.png)

### <a name="create-a-trunk-and-provision-users"></a>Créer une jonction et approvisionner des utilisateurs

Avec la version initiale du routage direct, Microsoft nécessitait l’ajout d’une jonction à chaque locataire servi (locataire client) à l’aide de l’applet de commande New-CSOnlinePSTNGateway.

Toutefois, cette méthode n’a pas été optimale pour deux raisons :
 
- **Gestion des frais généraux**. Le déchargement ou le drainage d’un SBC, par exemple, modifie certains paramètres, comme l’activation ou la désactivation de la déviation du trafic multimédia. La modification du port nécessite la modification des paramètres dans plusieurs locataires (en exécutant Set-CSOnlinePSTNGateway), mais il s’agit en fait du même SBC. 

-  **Traitement de la surcharge**. Collecte et surveillance des données d’intégrité des tronçons : les options SIP collectées à partir de plusieurs jonctions logiques qui sont, en réalité, le même SBC et la même jonction physique, ralentissent le traitement des données de routage.
 
Sur la base de ces commentaires, Microsoft apporte une nouvelle logique de provisionnement des jonctions pour les locataires clients.

Deux nouvelles entités ont été introduites :

- Jonction de transporteur inscrite dans le locataire de l’opérateur à l’aide de la commande New-CSOnlinePSTNGateway. Par exemple : 
   
   ```PowerShell
   New-CSOnlinePSTNGateway -FQDN customers.adatum.biz -SIPSignalingport 5068 -ForwardPAI $true
    ```

- Tronçon dérivé qui ne nécessite pas d’inscription. Il s’agit simplement d’un nom d’hôte souhaité ajouté dans à partir de la jonction de transporteur. Il dérive tous ses paramètres de configuration de la jonction de l’opérateur. L’association avec la jonction de transporteur est basée sur le nom de nom de domaine complet (voir les détails ci-dessous).

**Logique d’approvisionnement et exemple**

- Les opérateurs doivent configurer et gérer une seule jonction (la jonction d’opérateur dans le domaine de l’opérateur) à l’aide de la commande Set-CSOnlinePSTNGateway. Dans l’exemple ci-dessus, il s’agit adatum.biz.

- Dans le locataire du client, l’opérateur doit ajouter le nom de domaine complet de jonction dérivé aux itinéraires vocaux. Il n’est pas nécessaire d’exécuter New-CSOnlinePSTNGateway pour une jonction.

- La jonction dérivée, comme son nom l’indique, hérite ou dérive tous les paramètres de configuration de la jonction de l’opérateur. 

Exemples:
- Customers.adatum.biz : jonction de transporteur qui doit être créée dans le locataire de l’opérateur.

- Sbc1.customers.adatum.biz : jonction dérivée dans un locataire client. Vous pouvez ajouter le nom de la jonction dérivée dans le locataire client dans les itinéraires vocaux sans le créer.

- L’opérateur doit configurer un enregistrement DNS résolvant le nom de domaine complet de jonction dérivé en adresse IP SBC de l’opérateur.

- Toutes les modifications apportées sur une jonction de transporteur (sur le locataire de l’opérateur) sont automatiquement appliquées aux jonctions dérivées. Par exemple, les opérateurs peuvent modifier un port SIP sur la jonction de l’opérateur, et cette modification s’applique à toutes les jonctions dérivées. La nouvelle logique de configuration des jonctions simplifie la gestion, car vous n’avez pas besoin d’accéder à chaque locataire et de modifier le paramètre sur chaque jonction.

- Les options sont envoyées uniquement au nom de domaine complet de la jonction du transporteur. L’état d’intégrité de la jonction de transporteur est appliqué à toutes les jonctions dérivées et est utilisé pour les décisions de routage. En savoir plus sur les [options de routage direct](./direct-routing-monitor-and-troubleshoot.md).

- Le porteur peut drainer le tronc porteur, et tous les tronçons dérivés seront également drainés. 
 
> [!NOTE]
> Les règles de traduction de nombre appliquées sur la jonction de transporteur ne s’appliquent pas aux jonctions dérivées. Il s’agit d’un problème connu. Comme solution alternative, des règles de traduction de nombre doivent être créées pour le locataire de chaque client.

**Migration du modèle précédent vers la jonction de transporteur**
 
Pour la migration de l’implémentation actuelle du modèle hébergé par l’opérateur vers le nouveau modèle, les opérateurs doivent reconfigurer les jonctions pour les locataires clients. Supprimez les jonctions des locataires clients à l’aide de Remove-CSOnlinePSTNGateway (en laissant la jonction dans le locataire de l’opérateur) -

Nous encourageons vivement la migration vers la nouvelle solution dès que possible, car nous améliorerons la surveillance et l’approvisionnement à l’aide du transporteur et du modèle de jonction dérivé.
 
Pour plus d’informations sur la configuration de l’envoi du nom de domaine complet des sous-domaines dans l’en-tête Contact, consultez les [instructions du fournisseur SBC](#deploy-and-configure-the-sbc).

## <a name="considerations-for-setting-up-multi-tenant-failover"></a>Considérations relatives à la configuration du basculement multilocataire 

Pour configurer le basculement pour un environnement multilocataire, vous devez effectuer les opérations suivantes :

- Pour chaque locataire, ajoutez les noms de domaine complets pour deux SBC différents. Par exemple :

   customer1.sbc1.contoso.com <br>
   customer1.sbc2.contoso.com <br>

- Dans Les itinéraires vocaux en ligne, spécifiez les deux SBC. En cas d’échec d’un SBC, la stratégie de routage route les appels vers le deuxième SBC.


## <a name="see-also"></a>Voir aussi

[Planifier le routage direct](direct-routing-plan.md)

[Configurer le routage direct](direct-routing-configure.md)
