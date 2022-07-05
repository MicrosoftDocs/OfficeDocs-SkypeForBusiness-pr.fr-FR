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
description: Découvrez comment configurer un contrôleur de frontière de session (SBC) pour servir plusieurs locataires pour les partenaires Microsoft et/ou les opérateurs RTC.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9221414053b0ee92b87553e0f81c23b41b23f0fb
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/05/2022
ms.locfileid: "66616340"
---
# <a name="configure-a-session-border-controller-for-multiple-tenants"></a>Configurer un contrôleur de frontière de session pour plusieurs clients

Le routage direct prend en charge la configuration d’un contrôleur de bordure de session (SBC) pour servir plusieurs locataires.

> [!NOTE]
> Ce scénario est conçu pour les partenaires Microsoft et/ou les opérateurs RTC, appelés opérateurs plus loin dans ce document. Un opérateur vend des services de téléphonie fournis à Microsoft Teams à ses clients. 

Un opérateur :
- Déploie et gère un SBC dans son centre de données (les clients n’ont pas besoin d’implémenter un SBC et reçoivent des services de téléphonie de l’opérateur dans le client Teams).
- Interconnecte le SBC à plusieurs locataires.
- Fournit des services de réseau téléphonique commuté (RTC) publics aux clients.
- Gère la qualité des appels de bout en bout.
- Frais distincts pour les services RTC.

Microsoft ne gère pas les opérateurs. Microsoft propose un système téléphonique (PBX) et un client Teams. Microsoft certifie également les téléphones et certifie les SBC qui peuvent être utilisés avec le système téléphonique. Avant de choisir un opérateur, assurez-vous que votre choix dispose d’un SBC certifié et qu’il peut gérer la qualité de la voix de bout en bout.

Voici les étapes d’implémentation technique pour configurer le scénario.

**Opérateur uniquement :**
1. Déployez le SBC et configurez-le pour le scénario d’hébergement conformément aux [instructions des fournisseurs SBC certifiés](#deploy-and-configure-the-sbc).
2. Inscrivez un nom de domaine de base dans le locataire de l’opérateur et demandez un certificat générique.
3. Inscrivez un sous-domaine pour chaque client, qui fait partie du domaine de base.

**Opérateur avec un administrateur général client :**
1. Ajoutez le nom du sous-domaine au locataire client.
2. Activez le nom du sous-domaine.
3. Configurez la jonction du transporteur vers le locataire client et approvisionnez les utilisateurs.

*Veillez à comprendre les principes de base du DNS et la façon dont le nom de domaine est géré dans Microsoft 365. Consultez [obtenir de l’aide sur les domaines Microsoft 365](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) avant de continuer.*

## <a name="deploy-and-configure-the-sbc"></a>Déployer et configurer le SBC

Pour obtenir des instructions détaillées sur le déploiement et la configuration de SBC pour un scénario d’hébergement SBC, consultez la documentation du fournisseur SBC.

- **AudioCodes :** Consultez les [notes de configuration du routage direct](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams) pour la configuration du scénario d’hébergement SBC, comme décrit dans la note de configuration du modèle d’hébergement de routage direct microsoft Teams « Connecting AudioCodes SBC to Microsoft Teams Hosting Model ». 
- **Oracle:** Consultez les [notes de configuration du routage direct](https://www.oracle.com/technetwork/indexes/documentation/acme-packet-2228107.html) pour la configuration du scénario d’hébergement SBC, comme décrit dans la section « Microsoft ». 
- **Communications du ruban :** Pour obtenir de la documentation sur la configuration des [SBC Core SBC Core SBC](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe) De ruban, consultez la documentation sur la configuration des SBC de la série Ribbon Core. Voir aussi [La meilleure pratique du ruban - Configuration des opérateurs pour Microsoft Teams Direct Routing SBC Edge](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Direct+Routing+Carrier)
- **TE-Systems (anynode) :** Inscrivez-vous sur le site de [la page communauté TE-Systems](https://community.te-systems.de/) pour obtenir de la documentation et des exemples sur la configuration de anynode SBC pour plusieurs locataires.
- **Métaswitch :** Inscrivez-vous sur le site de [la page De la communauté Metaswitch](https://manuals.metaswitch.com/MAN39555) pour obtenir de la documentation sur l’activation de Perimeta SBC pour plusieurs locataires.

> [!NOTE]
> Veillez à savoir comment configurer l’en-tête « Contact ». L’en-tête Contact est utilisé pour rechercher le locataire client sur le message d’invitation entrant. 

## <a name="register-a-base-domain-and-subdomains"></a>Inscrire un domaine de base et des sous-domaines

Pour le scénario d’hébergement, vous devez créer :

- Un nom de domaine de base appartenant au transporteur.
- Sous-domaine qui fait partie du nom de domaine de base dans chaque locataire client.

Dans l’exemple suivant :

- Adatum est un opérateur qui sert plusieurs clients en fournissant des services Internet et de téléphonie.
- Woodgrove Bank, Contoso et Adventure Works sont trois clients qui ont des domaines Microsoft 365, mais qui reçoivent les services de téléphonie d’Adatum.

Les sous-domaines **DOIVENT** correspondre au nom de domaine complet de la jonction qui sera configurée pour le client et au nom de domaine complet dans l’en-tête Contact lors de l’envoi de l’invitation à Microsoft 365. 

Lorsqu’un appel arrive à l’interface de routage direct Microsoft 365, l’interface utilise l’en-tête Contact pour rechercher le locataire où l’utilisateur doit être recherché. Le routage direct n’utilise pas la recherche de numéro de téléphone sur l’invite, car certains clients peuvent avoir des numéros non DID qui peuvent se chevaucher dans plusieurs locataires. Par conséquent, le nom de nom de domaine complet dans l’en-tête Contact est nécessaire pour identifier le locataire exact pour rechercher l’utilisateur par le numéro de téléphone.

*Pour plus d’informations sur la création de noms de domaine dans les organisations Microsoft 365, consultez [Obtenir de l’aide sur les domaines Microsoft 365](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).*

Le diagramme suivant récapitule les exigences relatives au domaine de base, aux sous-domaines et à l’en-tête Contact.

:::image type="content" source="media/direct-routing-1-sbc-requirements.png" alt-text="Diagramme montrant la configuration requise pour les domaines et l’en-tête Contact." lightbox="media/direct-routing-1-sbc-requirements.png":::

Le SBC nécessite un certificat pour authentifier les connexions. Pour le scénario d’hébergement SBC, l’opérateur doit demander un certificat avec CN et/ou SAN *\*.base_domain (par exemple, \*.customers.adatum.biz).* Ce certificat peut être utilisé pour authentifier les connexions à plusieurs locataires servis à partir d’un seul SBC.

Le tableau suivant est un exemple d’une configuration.


|Nouveau nom de domaine |Type|Enregistré  |Certificat CN/SAN pour SBC  |Domaine par défaut du locataire dans l’exemple  |Nom de nom de domaine complet que SBC doit présenter dans l’en-tête Contact lors de l’envoi d’appels aux utilisateurs|
|---------|---------|---------|---------|---------|---------|
|customers.adatum.biz|    Base     |     Dans le locataire du transporteur  |    \*.customers.adatum.biz  |   adatum.biz      |NA, il s’agit d’un locataire de service, aucun utilisateur |
|sbc1.customers.adatum.biz|    Sous-domaine  |    Dans un locataire client  |    \*.customers.adatum.biz  | woodgrovebank.us  |  sbc1.customers.adatum.biz|
|sbc2.customers.adatum.biz  |   Sous-domaine | Dans un locataire client   |   \*.customers.adatum.biz   |contoso.com   |sbc2.customers.adatum.biz |
|sbc3.customers.adatum.biz |   Sous-domaine | Dans un locataire client |   \*.customers.adatum.biz  |  adventureworks.com | sbc3.customers.adatum.biz |

Pour configurer la base et les sous-domaines, suivez les étapes décrites ci-dessous. Cet exemple configure un nom de domaine de base (customers.adatum.biz) et un sous-domaine pour un client (sbc1.customers.adatum.biz dans le locataire woodgrove Bank).

> [!NOTE]
> Utilisez sbcX.customers.adatum.biz pour activer la voix dans le locataire de l’opérateur ; sbcX peut être n’importe quel nom d’hôte alphanumérique unique et valide.

## <a name="register-a-base-domain-name-in-the-carrier-tenant"></a>Inscrire un nom de domaine de base dans le locataire de l’opérateur

**Ces actions sont effectuées dans le locataire du transporteur.**

### <a name="ensure-that-you-have-appropriate-rights-in-the-carrier-tenant"></a>Assurez-vous que vous disposez des droits appropriés dans le locataire du transporteur

Vous ne pouvez ajouter de nouveaux domaines que si vous vous êtes connecté à l’Centre d'administration Microsoft 365 en tant qu’administrateur général. 

Pour valider le rôle que vous avez, connectez-vous au Centre d'administration Microsoft 365 (https://portal.office.com)accédez à **Utilisateurs** > **actifs utilisateurs**, puis vérifiez que vous disposez d’un rôle d’administrateur général. 

Pour plus d’informations sur les rôles d’administrateur et sur l’attribution d’un rôle dans Microsoft 365, consultez [À propos des rôles d’administrateur](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).

### <a name="add-a-base-domain-to-the-tenant-and-verify-it"></a>Ajouter un domaine de base au locataire et le vérifier

1. Dans le Centre d'administration Microsoft 365, accédez à **Configurer** > **domaines** > **Ajouter un domaine**.

2. Dans la zone **Entrée d’un domaine que vous possédez** , tapez le nom de domaine complet du domaine de base. Dans l’exemple suivant, le domaine de base est *customers.adatum.biz*.

3. Cliquez sur **Suivant**.

4. Dans cet exemple, le locataire a déjà adatum.biz en tant que nom de domaine vérifié. L’Assistant ne demande pas de vérification supplémentaire, car customers.adatum.biz est un sous-domaine pour le nom déjà inscrit. Toutefois, si vous ajoutez un nom de domaine complet qui n’a pas été vérifié auparavant, vous devez passer par le processus de vérification. Le processus de vérification est [décrit ci-dessous](#add-a-subdomain-to-the-customer-tenant-and-verify-it).

5. Sélectionnez **Suivant** et, dans la page **Mettre à jour les paramètres DNS** , sélectionnez **J’ajouterai moi-même les enregistrements DNS** , puis sélectionnez **Suivant**.

6. Dans la page suivante, effacez toutes les valeurs (sauf si vous souhaitez utiliser le nom de domaine pour Exchange, SharePoint, Teams ou Skype Entreprise), sélectionnez **Suivant**, puis sélectionnez **Terminer**. Vérifiez que votre nouveau domaine est dans l’état complet du programme d’installation.

### <a name="activate-the-domain-name"></a>Activer le nom de domaine

Une fois que vous avez inscrit un nom de domaine, vous devez l’activer en ajoutant au moins un compte d’utilisateur ou de ressource sous licence Teams. Les comptes acceptables sont concédés sous licence avec l’une des références SKU suivantes :

- Compte d’utilisateur avec Office 365 E1/E3/E5/A3/A5 ou Microsoft 365 E3/E5/A3/A5
- Compte d’utilisateur avec Office 365 F1/F3 ou Microsoft 365 F1/F3
- Compte d’utilisateur avec téléphone de zone commune
- Compte de ressource avec **licence de compte de ressource Téléphonie Microsoft Teams**

En outre, l’UPN du compte (nom d’utilisateur principal) ou Skype Entreprise’adresse SIP locale doit utiliser le même nom de domaine complet que le domaine nouvellement créé.

Pour plus d’informations sur l’ajout d’utilisateurs dans les organisations Microsoft 365, consultez [Obtenir de l’aide sur les domaines Microsoft 365](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).

Par exemple : test@customers.adatum.biz

![Capture d’écran de la page d’activation du domaine de base.](media/direct-routing-4-sbc-domain-activation.png)

## <a name="register-a-subdomain-name-in-a-customer-tenant"></a>Inscrire un nom de sous-domaine dans un locataire client

Vous devez créer un nom de sous-domaine unique pour chaque client. Dans cet exemple, nous allons créer un sous-domaine sbc1.customers.adatum.biz dans un locataire avec le nom de domaine par défaut woodgrovebank.us.

**Toutes les actions ci-dessous se trouvent dans le locataire du client.**

### <a name="ensure-that-you-have-appropriate-rights-in-the-customer-tenant"></a>Vérifiez que vous disposez des droits appropriés dans le locataire du client

Vous ne pouvez ajouter de nouveaux domaines que si vous vous êtes connecté à l’Centre d'administration Microsoft 365 en tant qu’administrateur général. 

Pour valider le rôle que vous avez, connectez-vous au Centre d'administration Microsoft 365 (https://portal.office.com)accédez à **Utilisateurs** > **actifs utilisateurs**, puis vérifiez que vous disposez d’un rôle d’administrateur général. 

Pour plus d’informations sur les rôles d’administrateur et sur l’attribution d’un rôle dans Microsoft 365, consultez [À propos des rôles d’administrateur](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).

### <a name="add-a-subdomain-to-the-customer-tenant-and-verify-it"></a>Ajouter un sous-domaine au locataire client et le vérifier

1. Dans le Centre d'administration Microsoft 365, accédez à **Configurer** > **domaines** > **Ajouter un domaine**.

2. Dans la zone **Entrée d’un domaine que vous possédez** , tapez le nom de domaine complet du sous-domaine de ce locataire. Dans l’exemple ci-dessous, le sous-domaine est sbc1.customers.adatum.biz.

3. Sélectionnez **Suivant**.

4. Le nom de domaine complet n’a jamais été inscrit dans le locataire. À l’étape suivante, vous devez vérifier le domaine. Sélectionnez **à la place Ajouter un enregistrement TXT**. 

5. Sélectionnez **Suivant**, puis notez la valeur TXT générée pour vérifier le nom de domaine.

    ![Capture d’écran des enregistrements texte sur la page Vérifier le domaine.](media/direct-routing-7-sbc-verify-domain-txt.png)

6. Créez l’enregistrement TXT avec la valeur de l’étape précédente dans le fournisseur d’hébergement DNS de l’opérateur.

    Pour plus d’informations, consultez [Créer des enregistrements DNS auprès de n’importe quel fournisseur d’hébergement DNS](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166).

7. Accédez au Centre d'administration Microsoft 365 du client et **sélectionnez Vérifier**. 

8. Sur la page suivante, sélectionnez **J’ajouterai moi-même les enregistrements DNS** , puis **sélectionnez Suivant**.

9. Dans la page **Choisir votre services en ligne, effacez** toutes les options et sélectionnez **Suivant**.

10. Sélectionnez **Terminer** dans la page **Mettre à jour les paramètres DNS** .

11. Vérifiez que l’état est **terminé**.

    ![Capture d’écran de la page montrant l’état de l’installation terminée.](media/direct-routing-12-sbc-setup-complete.png)

> [!NOTE]
> L’URL de base et le sous-domaine du client individuel doivent se trouver sur le même locataire pour vous permettre d’ajouter une jonction de _route directe_ .

### <a name="activate-the-subdomain-name"></a>Activer le nom du sous-domaine

Une fois que vous avez inscrit un nom de sous-domaine, vous devez l’activer en ajoutant au moins un compte d’utilisateur ou de ressource sous licence Teams. Les comptes acceptables sont concédés sous licence avec l’une des références SKU suivantes :

-   Compte d’utilisateur avec Office 365 E1/E3/E5/A3/A5 ou Microsoft 365 E3/E5/A3/A5
-   Compte d’utilisateur avec Office 365 F1/F3 ou Microsoft 365 F1/F3
-   Compte d’utilisateur avec téléphone de zone commune
-   Compte de ressource avec une licence **de compte de ressource Téléphonie Microsoft Teams**

En outre, l’UPN du compte (nom d’utilisateur principal) ou Skype Entreprise’adresse SIP locale doit utiliser le même nom de domaine complet que le sous-domaine nouvellement créé.

Pour plus d’informations sur l’ajout d’utilisateurs dans les organisations Microsoft 365, consultez [Obtenir de l’aide sur Microsoft 365](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).

Par exemple : test@sbc1.customers.adatum.biz

![Capture d’écran de la page Activation du sous-domaine.](media/direct-routing-13-sbc-activate-subdomain.png)

### <a name="create-a-trunk-and-provision-users"></a>Créer une jonction et approvisionner des utilisateurs

Avec la version initiale du routage direct, Microsoft a requis l’ajout d’une jonction à chaque locataire (client client) servi à l’aide de l’applet de commande New-CSOnlinePSTNGateway.

Toutefois, cette méthode ne s’est pas avérée optimale pour deux raisons :
 
- **Gestion des surcharges**. Le déchargement ou le drainage d’un SBC, par exemple, modifie certains paramètres, tels que l’activation ou la désactivation de la déviation du trafic multimédia. La modification du port nécessite de modifier les paramètres dans plusieurs locataires (en exécutant Set-CSOnlinePSTNGateway), mais il s’agit en fait du même SBC. 

-  **Traitement de la surcharge**. Collecte et surveillance des données d’intégrité des jonctions : les options SIP collectées à partir de plusieurs jonctions logiques qui sont, en réalité, le même SBC et la même jonction physique, ralentissent le traitement des données de routage.
 
Sur la base de ces commentaires, Microsoft apporte une nouvelle logique pour approvisionner les jonctions pour les locataires du client.

Deux nouvelles entités ont été introduites :

- Jonction de transporteur inscrite dans le locataire du transporteur à l’aide de la commande New-CSOnlinePSTNGateway. Par exemple : 
   
   ```PowerShell
   New-CSOnlinePSTNGateway -FQDN customers.adatum.biz -SIPSignalingport 5068 -ForwardPAI $true
    ```

- Jonction dérivée qui ne nécessite pas d’inscription. Il s’agit simplement d’un nom d’hôte souhaité ajouté à partir de la jonction de transporteur. Il dérive tous ses paramètres de configuration de la jonction de transporteur. L’association avec la jonction de transporteur est basée sur le nom de nom de domaine complet (voir les détails ci-dessous).

**Logique d’approvisionnement et exemple**

- Les transporteurs doivent configurer et gérer une seule jonction (la jonction de transporteur dans le domaine du transporteur) à l’aide de la commande Set-CSOnlinePSTNGateway. Dans l’exemple ci-dessus, il est adatum.biz.

- Dans le locataire client, le transporteur doit ajouter le nom de domaine complet de jonction dérivé aux itinéraires vocaux. Il n’est pas nécessaire d’exécuter New-CSOnlinePSTNGateway pour une jonction.

- La jonction dérivée, comme son nom l’indique, hérite ou dérive tous les paramètres de configuration de la jonction de transporteur. 

Exemples:
- Customers.adatum.biz : jonction de transporteur qui doit être créée dans le locataire du transporteur.

- Sbc1.customers.adatum.biz : jonction dérivée dans un locataire client. Vous pouvez ajouter le nom de la jonction dérivée dans le locataire client dans la stratégie de routage vocal en ligne sans le créer.

- Le transporteur doit configurer l’enregistrement DNS résolvant le nom de domaine complet de jonction dérivé en adresse IP SBC du transporteur.

- Toutes les modifications apportées à une jonction de transporteur (sur le locataire du transporteur) sont automatiquement appliquées aux jonctions dérivées. Par exemple, les transporteurs peuvent modifier un port SIP sur la jonction du transporteur, et cette modification s’applique à toutes les jonctions dérivées. Une nouvelle logique pour configurer les jonctions simplifie la gestion, car vous n’avez pas besoin d’accéder à chaque locataire et de modifier le paramètre sur chaque jonction.

- Les options sont envoyées uniquement au nom de domaine complet de la jonction de transporteur. L’état d’intégrité du tronçon porteur est appliqué à toutes les jonctions dérivées et est utilisé pour les décisions de routage. En savoir plus sur les [options de routage direct](./direct-routing-monitor-and-troubleshoot.md).

- Le transporteur peut drainer la jonction de transporteur, et toutes les jonctions dérivées seront également drainées. 
 
> [!NOTE]
> Les règles de traduction de nombre appliquées sur la jonction de transporteur ne s’appliquent pas aux jonctions dérivées. Il s’agit d’un problème connu. Comme solution alternative, des règles de traduction de nombres doivent être créées pour le locataire de chaque client.

**Migration du modèle précédent vers la jonction de transporteur**
 
Pour la migration de l’implémentation actuelle du modèle hébergé par l’opérateur vers le nouveau modèle, les opérateurs devront reconfigurer les jonctions pour les locataires des clients. Supprimez les jonctions des locataires clients à l’aide de Remove-CSOnlinePSTNGateway (en laissant la jonction dans le locataire du transporteur)-

Nous encourageons vivement la migration vers la nouvelle solution dès que possible, car nous améliorerons la surveillance et l’approvisionnement à l’aide du transporteur et du modèle de jonction dérivé.
 
Pour plus d’informations sur la configuration de l’envoi du nom de domaine complet des sous-domaines dans l’en-tête Contact, consultez les [instructions du fournisseur SBC](#deploy-and-configure-the-sbc).

## <a name="considerations-for-setting-up-multi-tenant-failover"></a>Considérations relatives à la configuration du basculement multilocataire 

Pour configurer le basculement pour un environnement multilocataire, vous devez effectuer les opérations suivantes :

- Pour chaque locataire, ajoutez les noms de domaine complets pour deux SBC différents. Par exemple :

   customer1.sbc1.contoso.com <br>
   customer1.sbc2.contoso.com <br>

- Dans les itinéraires vocaux en ligne, spécifiez les deux SBC. Si un SBC échoue, la stratégie de routage route les appels vers le deuxième SBC.


## <a name="see-also"></a>Voir aussi

[Planifier le routage direct](direct-routing-plan.md)

[Configurer le routage direct](direct-routing-configure.md)
