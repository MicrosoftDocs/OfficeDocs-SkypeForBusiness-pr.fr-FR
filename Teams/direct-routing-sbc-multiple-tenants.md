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
description: Découvrez comment configurer un contrôleur de session en bordure (SBC) pour servir plusieurs clients à des partenaires Microsoft et/ou des opérateurs PSTN.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 59a17da1a1fb77bbe30c79831480014fe1278bae
ms.sourcegitcommit: 2e8daa3511cd198b3e0d43b153dd37a59cb21692
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/11/2022
ms.locfileid: "62763359"
---
# <a name="configure-a-session-border-controller-for-multiple-tenants"></a>Configurer un contrôleur de frontière de session pour plusieurs clients

Le routage direct prend en charge la configuration d’un contrôleur de session en bordure (SBC) pour servir plusieurs locataires.

> [!NOTE]
> Ce scénario est conçu pour les partenaires microsoft et/ou les opérateurs PSTN, appelés opérateurs plus loin dans ce document. Un opérateur vend des services téléphoniques livrés Microsoft Teams à ses clients. 

Opérateur :
- Déploie et gère un SBC dans leur centre de données (les clients n’ont pas besoin d’implémenter un SBC et reçoivent des services de téléphonie de l’opérateur dans le client Teams).
- Connecte le SBC à plusieurs locataires.
- Fournit des services de réseau téléphonique commuté (PSTN) aux clients.
- Gère la qualité des appels de bout en bout.
- Frais distincts pour les services PSTN.

Microsoft ne gère pas les opérateurs. Microsoft propose Système téléphonique (une branche privée Exchange (PBX) et un client Teams client. Microsoft certifie également les téléphones et certifie les SBCs qui peuvent être utilisés avec Système téléphonique. Avant de choisir un opérateur, assurez-vous que votre choix dispose d’un SBC certifié et pouvez gérer la qualité vocale de bout en bout.

Voici les étapes d’implémentation technique pour configurer le scénario.

**Opérateur uniquement :**
1. Déployez le SBC et configurez-le pour le scénario d’hébergement conformément aux [instructions des fournisseurs SBC certifiés](#deploy-and-configure-the-sbc).
2. Enregistrez un nom de domaine de base auprès du client de l’opérateur et demandez un certificat générique.
3. Enregistrez un sous-domaine pour chaque client, qui fait partie du domaine de base.

**Opérateur auprès d’un administrateur général du client :**
1. Ajoutez le nom du sous-domaine au client.
2. Activez le nom du sous-domaine.
3. Configurez la ligne entre l’opérateur et le client client et configurez les utilisateurs.

*Assurez-vous de comprendre les principes de base du DNS et la manière dont le nom de domaine est géré dans Microsoft 365. Voir [Obtenir de l’aide Microsoft 365 domaines particuliers](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) avant de poursuivre.*

## <a name="deploy-and-configure-the-sbc"></a>Déployer et configurer le SBC

Pour obtenir la procédure détaillée de déploiement et de configuration des SBC pour un scénario d’hébergement SBC, consultez la documentation du fournisseur SBC.

- **AudioCodes** : - Consultez les [notes de configuration](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams) du routage direct pour la configuration du scénario d’hébergement SBC, comme décrit dans la description « Connexion de AudioCodes SBC à Microsoft Teams Note de configuration du modèle d’hébergement de routage direct ». 
- **Oracle :** - Consultez [les notes de configuration du routage direct](https://www.oracle.com/technetwork/indexes/documentation/acme-packet-2228107.html) pour la configuration du scénario d’hébergement SBC, comme décrit dans la section « Microsoft ». 
- **Communications sur le ruban :** [Consultez le guide de configuration](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe) du centre Microsoft Teams Communications du ruban pour obtenir de la documentation sur la configuration des SBCs core de séries du ruban. Voir aussi [Meilleures pratiques du ruban - Configuration des opérateurs pour Microsoft Teams du bord SBC de routage direct](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Direct+Routing+Carrier)
- **SYSTÈMES TE (anynode) : inscrivez-vous** sur le site de [la page Community TE-Systems](https://community.te-systems.de/) pour obtenir de la documentation et des exemples sur la configuration d’un SBC anynode pour plusieurs locataires.
- **Metaswitch :** - Inscrivez-vous sur le site [de Community de la page](https://manuals.metaswitch.com/MAN39555) pour obtenir de la documentation sur la façon d’activer SBC Perimeta pour plusieurs locataires.

> [!NOTE]
> Assurez-vous de savoir comment configurer l’en-tête « Contact ». L’en-tête Contact est utilisé pour rechercher le client dans le message d’invitation entrante. 

## <a name="register-a-base-domain-and-subdomains"></a>Enregistrer un domaine de base et des sous-domaines

Pour le scénario d’hébergement, vous devez créer :

- Un nom de domaine de base propriété de l’opérateur.
- Sous-domaine faisant partie du nom de domaine de base de chaque client.

Dans l’exemple suivant :

- Adatum est un opérateur qui sert plusieurs clients en fournissant des services Internet et téléphoniques.
- Woodgrove Bank, Contoso et Adventure Works sont trois clients qui ont des domaines Microsoft 365, mais qui reçoivent les services de téléphonie d’Adatum.

Les sous-domaine **DOIVENT** correspondre au nom de nom de domaine complet (FQDN) de la ligne qui sera configurée pour le client et au nom de domaine complet dans l’en-tête Contact lors de l’envoi de l’invitation à Microsoft 365. 

Lorsqu’un appel arrive dans l’interface Microsoft 365 routage direct, l’interface utilise l’en-tête Contact pour trouver le client dans lequel l’utilisateur doit être cherché. Le routage direct n’utilise pas la recherche de numéros de téléphone dans l’invitation, car certains clients peuvent avoir des numéros non DID qui peuvent se chevaucher dans plusieurs clients. Par conséquent, le nom de nom de domaine complet dans l’en-tête du contact est nécessaire pour identifier le client exact à rechercher sur le numéro de téléphone de l’utilisateur.

*Pour plus d’informations sur la création de noms de Microsoft 365 dans les organisations, voir Obtenir de l’aide [sur Microsoft 365 domaines.](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef)*

Le diagramme suivant récapitule les conditions requises pour baser le domaine, les sous-domaines et l’en-tête des contacts.

![Diagramme montrant les exigences relatives aux domaines et à l’en-tête des contacts.](media/direct-routing-1-sbc-requirements.png)

Le SBC requiert un certificat pour authentifier les connexions. Dans le cas d’un scénario d’hébergement SBC, l’opérateur doit demander un certificat auprès de CN et/ou SAN *\*.base_domain (par exemple, \*.customers.adatum.biz).* Ce certificat peut être utilisé pour authentifier les connexions à plusieurs locataires servis à partir d’un même SBC.

Le tableau suivant est un exemple de configuration.


|Nouveau nom de domaine |Type|Inscrit  |Certificat CN/SAN pour SBC  |Domaine par défaut du client dans l’exemple  |Nom de nom de domaine complet que SBC doit présenter dans l’en-tête de contact lors de l’envoi d’appels à des utilisateurs|
|---------|---------|---------|---------|---------|---------|
|customers.adatum.biz|    Base     |     Dans le client de l’opérateur  |    \*.customers.adatum.biz  |   adatum.biz      |NA, il s’agit d’un client de service, aucun utilisateur |
|sbc1.customers.adatum.biz|    Sous-domaine  |    Dans un client  |    \*.customers.adatum.biz  | woodgrovebank.us  |  sbc1.customers.adatum.biz|
|sbc2.customers.adatum.biz  |   Sous-domaine | Dans un client   |   \*.customers.adatum.biz   |contoso.com   |sbc2.customers.adatum.biz |
|sbc3.customers.adatum.biz |   Sous-domaine | Dans un client |   \*.customers.adatum.biz  |  adventureworks.com | sbc3.customers.adatum.biz |
||         |         |         |         |         |

Pour configurer la base et les sous-domaine, suivez les étapes décrites ci-dessous. Cet exemple configure un nom de domaine de base (customers.adatum.biz) et un sous-domaine pour un client (sbc1.customers.adatum.biz dans le client Woodgrove Bank).

> [!NOTE]
> Utilisez sbcX.customers.adatum.biz pour activer la voix dans le client de l’opérateur ; sbcX peut être n’importe quel nom d’hôte alphanumérique unique et valide.

## <a name="register-a-base-domain-name-in-the-carrier-tenant"></a>Enregistrer un nom de domaine de base dans le client de l’opérateur

**Ces actions sont effectuées dans le client de l’opérateur.**

### <a name="ensure-that-you-have-appropriate-rights-in-the-carrier-tenant"></a>Vérifier que vous avez les droits appropriés dans le client de l’opérateur

Vous ne pouvez ajouter des domaines que si vous vous êtes inscrit au Centre d'administration Microsoft 365 en tant qu’administrateur général. 

Pour valider votre rôle, connectez-vous à la Centre d'administration Microsoft 365 (https://portal.office.com),  >  allez dans Utilisateurs utilisateurs **actifs, puis** vérifiez que vous avez un rôle Administrateur général. 

Pour plus d’informations sur les rôles d’administrateur et la manière d’attribuer un rôle dans Microsoft 365 rôles, voir À propos [des rôles d’administrateur](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).

### <a name="add-a-base-domain-to-the-tenant-and-verify-it"></a>Ajouter un domaine de base au client et le vérifier

1. Dans le Centre d'administration Microsoft 365, allez au **domaine** **SetupDomainsAdd** >  > .

2. Dans la **zone Entrer un domaine dont vous êtes** propriétaire, tapez le nom de domaine (FQDN) du domaine de base. Dans l’exemple suivant, le domaine de base est *customers.adatum.biz*.

3. Cliquez sur **Suivant**.

4. Dans cet exemple, le client dispose déjà d’adatum.biz nom de domaine vérifié. L’Assistant ne demande pas de vérification supplémentaire, customers.adatum.biz est un sous-domaine du nom déjà enregistré. Toutefois, si vous ajoutez un FQDN qui n’a pas été vérifié auparavant, vous devez passer par le processus de vérification. Le processus de vérification est décrit [ci-dessous](#add-a-subdomain-to-the-customer-tenant-and-verify-it).

5. **Sélectionnez Suivant**, puis sur la page Mettre à jour **DNS Paramètres** page, je vais ajouter moi-même les enregistrements **DNS**, puis **sélectionner Suivant**.

6. Dans la page suivante, effacer toutes les valeurs (sauf si vous voulez utiliser le nom de domaine pour Exchange, SharePoint, Teams ou Skype Entreprise), sélectionnez **Suivant, puis** **Terminer.** Assurez-vous que votre nouveau domaine est dans l’état final du programme d’installation.

### <a name="activate-the-domain-name"></a>Activer le nom de domaine

Une fois que vous avez enregistré un nom de domaine, vous devez l’activer en ajoutant au moins un utilisateur avec une licence Système téléphonique et en attribuant une adresse SIP avec la partie FQDN de l’adresse SIP correspondant au domaine de base créé.

> [!NOTE]
> Le client de l’opérateur doit conserver au moins Système téléphonique licence attribuée au client pour éviter la suppression de la configuration Skype Entreprise client. 

*Pour plus d’informations sur l’ajout d Microsoft 365 utilisateurs dans les organisations, voir Obtenir de l’aide [Microsoft 365 domaines.](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef)*

Par exemple : test@customers.adatum.biz

![Capture d’écran de la page d’activation du domaine de base.](media/direct-routing-4-sbc-domain-activation.png)

## <a name="register-a-subdomain-name-in-a-customer-tenant"></a>Enregistrer un nom de sous-domaine auprès d’un client

Vous devrez créer un nom de sous-domaine unique pour chaque client. Dans cet exemple, nous allons créer un sous-domaine sbc1.customers.adatum.biz client avec le nom de domaine par défaut woodgrovebank.us.

**Toutes les actions ci-dessous sont dans le client client.**

### <a name="ensure-that-you-have-appropriate-rights-in-the-customer-tenant"></a>Vérifier que vous avez les droits appropriés dans le client

Vous ne pouvez ajouter des domaines que si vous vous êtes inscrit au Centre d'administration Microsoft 365 en tant qu’administrateur général. 

Pour valider votre rôle, connectez-vous à la Centre d'administration Microsoft 365 (https://portal.office.com),  >  allez dans Utilisateurs utilisateurs **actifs, puis** vérifiez que vous avez un rôle Administrateur général. 

Pour plus d’informations sur les rôles d’administrateur et la manière d’attribuer un rôle dans Microsoft 365 rôles, voir À propos [des rôles d’administrateur](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).

### <a name="add-a-subdomain-to-the-customer-tenant-and-verify-it"></a>Ajouter un sous-domaine au client et le vérifier

1. Dans le Centre d'administration Microsoft 365, allez au **domaine** **SetupDomainsAdd** >  > .

2. Dans la **zone Entrer un domaine dont vous êtes** propriétaire, tapez le nom de domaine (FQDN) du sous-domaine de ce client. Dans l’exemple ci-dessous, le sous-domaine est sbc1.customers.adatum.biz.

3. **Sélectionnez Suivant**.

4. Le FQDN n’a jamais été enregistré dans le client. Dans l’étape suivante, vous devrez vérifier le domaine. **Sélectionnez Plutôt Ajouter un enregistrement TXT**. 

5. **Sélectionnez Suivant**, puis notez la valeur TXT générée pour vérifier le nom de domaine.

    ![Capture d’écran d’enregistrements texte dans la page Vérifier le domaine.](media/direct-routing-7-sbc-verify-domain-txt.png)

6. Créez l’enregistrement TXT avec la valeur de l’étape précédente du fournisseur d’hébergement DNS de l’opérateur.

    Pour plus d’informations, [voir Créer des enregistrements DNS chez un fournisseur d’hébergement DNS](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166).

7. Allez à la demande du Centre d'administration Microsoft 365 et sélectionnez **Vérifier**. 

8. Sur la page suivante, **sélectionnez J’ajoute les enregistrements DNS** moi-même, puis **Suivant**.

9. Dans la page **Choisir vos services en ligne** , effacer toutes les options et sélectionner **Suivant**.

10. **Sélectionnez Terminer** dans la page **Mettre à jour les paramètres DNS**.

11. Assurez-vous que le programme **d’installation est terminé**. 
    
    ![Capture d’écran de la page montrant l’état du programme d’installation terminé.](media/direct-routing-12-sbc-setup-complete.png)
    
> [!NOTE]
> L’URL de base et le sous-domaine du client doivent se trouver sur le même client pour pouvoir vous permettre d’ajouter une ligne _d’itinéraire_ directe.

### <a name="activate-the-subdomain-name"></a>Activer le nom du sous-domaine

Après avoir enregistré un nom de domaine, vous devez l’activer en ajoutant au moins un utilisateur et en attribuant une adresse SIP avec la partie nom de domaine complet de l’adresse SIP correspondant au sous-domaine créé dans le client. 

*Pour plus d’informations sur l’ajout d’utilisateurs Microsoft 365 organisations, voir [Obtenir de l’aide sur Microsoft 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef).*

Par exemple : test@sbc1.customers.adatum.biz

![Capture d’écran de la page Activation de la sous-domaine.](media/direct-routing-13-sbc-activate-subdomain.png)

### <a name="create-a-trunk-and-provision-users"></a>Créer une ligne et mettre en service des utilisateurs

Avec la version initiale du routage direct, Microsoft a demandé qu’une ligne soit ajoutée à chaque client servi (client client) à l’aide de l'New-CSOnlinePSTNGateway cmdlet.

Cependant, cette méthode n’est pas optimale pour deux raisons :
 
- **Gestion des frais**. Par exemple, le fait de décharger ou de décharger un SBC modifie certains paramètres, comme l’activation ou la désactivation de la dérivation média. La modification du port nécessite la modification des paramètres de plusieurs locataires (en exécutant Set-CSOnlinePSTNGateway), mais il s’agit en fait du même SBC. 

-  **Traitement des frais**. Collecte et surveillance des données d’intégrité de ligne - Les options SIP collectées à partir de plusieurs ligne logiques qui sont en réalité le même SBC et la même ligne physique ralentissent le traitement des données de routage.
 
Sur la base de ces commentaires, Microsoft apporte une nouvelle logique de mise en service des ligne pour les clients clients.

Deux nouvelles entités ont été introduites :

- Ligne d’opérateur inscrite dans le client de l’opérateur à l’aide de la commande New-CSOnlinePSTNGateway. Par exemple : 
   
   ```PowerShell
   New-CSOnlinePSTNGateway -FQDN customers.adatum.biz -SIPSignalingport 5068 -ForwardPAI $true
    ```

- Ligne dérivée qui ne nécessite pas d’inscription. Il s’agit simplement d’un nom d’hôte souhaité ajouté à partir de la ligne de l’opérateur. Il dérive tous ses paramètres de configuration de la ligne de l’opérateur. Il n’est pas nécessaire de créer la ligne dérivée dans PowerShell, et l’association avec la ligne de l’opérateur est basée sur le nom de nom de domaine complet (voir les détails ci-dessous).

**Logique d’approvisionnement et exemple**

- Les opérateurs doivent configurer et gérer une seule ligne (la ligne du transporteur dans le domaine de l’opérateur) à l’aide de Set-CSOnlinePSTNGateway ligne. Dans l’exemple ci-dessus, il adatum.biz.

- Dans le client client, l’opérateur doit ajouter le nom de fQDN de ligne dérivée aux stratégies de routage voix des utilisateurs. Il n’est pas nécessaire d’exécuter New-CSOnlinePSTNGateway une ligne.

- La ligne dérivée, comme son nom le suggère, hérite ou dérive tous les paramètres de configuration de la ligne d’opérateur. 

Exemples :
- Customers.adatum.biz ligne d’opérateur qui doit être créée dans le client de l’opérateur.

- Sbc1.customers.adatum.biz ligne dérivée dans un client client qui n’a pas besoin d’être créée dans PowerShell. Vous pouvez ajouter le nom de la ligne dérivée dans le client client dans la stratégie de routage voix en ligne sans la créer (utilisez le nom de domaine complet de ligne dérivée lors de la configuration d’une stratégie de routage vocal dans LE PROGRAMME.AUT sous Teams-Voice-Direct Routing-Voice Router le champ SBCs inscrits).

- Carrier devra configurer l’enregistrement DNS résolvant le nom de fQDN de ligne dérivée à l’adresse ip de l’opérateur SBC.

- Toutes les modifications apportées à une ligne d’opérateur (sur le client de l’opérateur) sont automatiquement appliquées aux ligne dérivées. Par exemple, les opérateurs peuvent modifier un port SIP sur la ligne du transporteur, et ce changement s’applique à toutes les ligne dérivées. Une nouvelle logique de configuration des ligne simplifie la gestion, car vous n’avez pas besoin d’aller à chaque client et de modifier le paramètre sur chaque ligne.

- Les options sont envoyées uniquement à la ligne d’opérateur FQDN. L’état d’état de la ligne du transporteur est appliqué à toutes les ligne dérivées et est utilisé pour les décisions de routage. En savoir plus sur [les options de routage direct](./direct-routing-monitor-and-troubleshoot.md).

- L’opérateur peut utiliser la ligne d’opérateur, et toutes les branches dérivées sont également désoutoutées. 
 
> [!NOTE]
> Les règles de traduction des nombres appliquées sur la ligne du transporteur ne s’appliquent pas aux ligne dérivées. Il s’agit d’un problème connu. Une autre solution consiste à créer des règles de traduction des nombres pour le client de chaque client.

**Migration du modèle précédent vers la ligne du transporteur**
 
Pour la migration de l’implémentation actuelle du modèle hébergé par l’opérateur vers le nouveau modèle, les opérateurs doivent reconfigurer les ligne pour les clients client. Supprimez les ligne des clients client à l’aide de Remove-CSOnlinePSTNGateway (en laissant la ligne dans le client de l’opérateur) -

Nous encourageons vivement la migration vers la nouvelle solution dès que possible, car nous améliorerons la surveillance et l’approvisionnement à l’aide de l’opérateur et du modèle de ligne dérivée.
 
Pour plus d’informations sur la configuration de l’envoi du nom de domaine complet (FQDN) des sous-domaine dans l’en-tête de contact, voir les [instructions pour les fournisseurs SBC](#deploy-and-configure-the-sbc).

## <a name="considerations-for-setting-up-multi-tenant-failover"></a>Considérations pour la configuration duover multi-client 

Pour configurer leover pour un environnement multi-client, vous devez faire les choses suivantes :

- Pour chaque client, ajoutez les FQDN pour deux SBCs différents. Par exemple :

   customer1.sbc1.contoso.com <br>
   customer1.sbc2.contoso.com <br>

- Dans les stratégies de routage voix en ligne des utilisateurs, spécifiez les deux SBCS. En cas d’échec d’un SBC, la stratégie de routage route les appels vers le deuxième SBC.


## <a name="see-also"></a>Voir aussi

[Planifier le routage direct](direct-routing-plan.md)

[Configurer le routage direct](direct-routing-configure.md)
