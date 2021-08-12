---
title: Configurer le contrôleur de bordure de session - Plusieurs locataires
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Découvrez comment configurer un contrôleur de session en bordure (SBC) pour servir plusieurs clients à des partenaires Microsoft et/ou des opérateurs PSTN.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c313ee09db068fca512a7f1c9c3478fad465ff4f9d64381f4f62790da4208ad2
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54293911"
---
# <a name="configure-a-session-border-controller-for-multiple-tenants"></a>Configurer un contrôleur de frontière de session pour plusieurs clients

Le routage direct prend en charge la configuration d’un contrôleur de session en bordure (SBC) pour servir plusieurs locataires.

> [!NOTE]
> Ce scénario est conçu pour les partenaires microsoft et/ou les opérateurs PSTN, appelés opérateurs plus loin dans ce document. Un opérateur vend des services téléphoniques livrés Microsoft Teams à ses clients. 

Opérateur :
- Déploie et gère un SBC dans leur centre de données (les clients n’ont pas besoin d’implémenter un SBC et reçoivent des services de téléphonie de l’opérateur dans le client Teams).
- Connecte le SBC à plusieurs locataires.
- Fournit des services PSTN aux clients.
- Gère la qualité des appels de bout en bout.
- Frais distincts pour les services PSTN.

Microsoft ne gère pas les opérateurs. Microsoft propose un système pbx (Téléphone Microsoft données) et un client Teams client. Microsoft certifie également les téléphones et certifie les SBCs qui peuvent être utilisés avec Téléphone Microsoft Système informatique. Avant de choisir un opérateur, assurez-vous que votre choix dispose d’un SBC certifié et que vous pouvez gérer la qualité vocale de bout en bout.

Voici les étapes d’implémentation technique que vous pouvez suivre pour configurer le scénario.

**Opérateur uniquement :**
1. Déployez le SBC et configurez-le pour le scénario d’hébergement conformément aux instructions des fournisseurs [SBC certifiés.](#deploy-and-configure-the-sbc)
2. Enregistrez un nom de domaine de base auprès du client de l’opérateur et demandez un certificat générique.
3. Enregistrez un sous-domaine pour chaque client, qui fait partie du domaine de base.

**Opérateur auprès d’un administrateur général du client :**
1. Ajoutez le nom du sous-domaine au client.
2. Activez le nom du sous-domaine.
3. Configurez la ligne entre l’opérateur et le client client et configurez les utilisateurs.

*Veillez à comprendre les principes de base du DNS et la manière dont le nom de domaine est géré dans Microsoft 365 ou Office 365. Voir [Obtenir de l’aide sur Microsoft 365 domaines Office 365 domaine particuliers](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) avant de poursuivre.*

## <a name="deploy-and-configure-the-sbc"></a>Déployer et configurer le SBC

Pour obtenir la procédure détaillée de déploiement et de configuration des SBC pour un scénario d’hébergement SBC, consultez la documentation du fournisseur SBC.

- **AudioCodes** : notes de [configuration](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams)du routage direct, configuration du scénario d’hébergement SBC décrit dans « Connexion de AudioCodes SBC à Microsoft Teams Note de configuration du modèle d’hébergement de routage direct ». 
- **Oracle :** [notes de configuration de routage directe,](https://www.oracle.com/technetwork/indexes/documentation/acme-packet-2228107.html)la configuration du scénario d’hébergement SBC est décrite dans la section « Microsoft ». 
- **Communications sur le ruban :**  Reportez-vous au guide de configuration du centre de Microsoft Teams [SBC](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe) sur les communications du ruban pour obtenir de la documentation sur la configuration des SBC de série principale du ruban et sur les meilleures pratiques du ruban dans le ruban - Configuration des opérateurs pour le Microsoft Teams SBC de [routage](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Direct+Routing+Carrier) direct
- **TE-Systems (anynode) :**  Inscrivez-vous sur la page des systèmes [TE Community pour](https://community.te-systems.de/) obtenir de la documentation et des exemples sur la configuration d’un SBC anynode pour plusieurs locataires.
- **Metaswitch :**  Inscrivez-vous sur [la page metaswitch Community pour](https://manuals.metaswitch.com/MAN39555) obtenir de la documentation sur la façon d’activer perimeta SBC pour plusieurs locataires.

> [!NOTE]
> Attention à la configuration de l’en-tête « Contact ». L’en-tête De contact est utilisé pour rechercher le client client dans le message d’invitation entrante. 

## <a name="register-a-base-domain-and-subdomains"></a>Enregistrer un domaine de base et des sous-domaines

Pour le scénario d’hébergement, vous devez créer :
- Un nom de domaine de base qui est la propriété de l’opérateur.
- Sous-domaine faisant partie du nom de domaine de base de chaque client.

Dans l’exemple suivant :
- Adatum est un opérateur qui sert plusieurs clients en fournissant des services Internet et téléphoniques.
- Woodgrove Bank, Contoso et Adventure Works sont trois clients qui ont des domaines Microsoft 365 ou Office 365 mais qui reçoivent les services téléphoniques d’Adatum.

Les sous-noms doivent correspondre au nom de nom de domaine complet (FQDN) de la ligne qui sera configurée pour le client et au nom de domaine complet dans l’en-tête Contact lors de l’envoi de l’invitation à Microsoft 365 ou Office 365.  

Lorsqu’un appel arrive dans l’interface de Microsoft 365 ou Office 365 Routage direct, l’interface utilise l’en-tête Contact pour trouver le client dans lequel l’utilisateur doit être cherché. Le routage direct n’utilise pas la recherche de numéro de téléphone dans l’invitation, car certains clients peuvent avoir des numéros non DID qui peuvent se chevaucher dans plusieurs clients. Par conséquent, le nom de nom de domaine complet dans l’en-tête du contact est nécessaire pour identifier le client exact sur la base du numéro de téléphone de l’utilisateur.

*Consultez [l’aide sur Office 365 domaines pour](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) plus d’informations sur la création de noms de domaine Microsoft 365 ou Office 365 organisation.*

Le diagramme suivant récapitule les conditions requises pour baser le domaine, les sous-domaines et l’en-tête des contacts.

![Diagramme montrant les exigences requises pour les domaines et l’en-tête des contacts](media/direct-routing-1-sbc-requirements.png)

Le SBC nécessite un certificat pour authentifier les connexions. Dans le cas d’un scénario d’hébergement SBC, l’opérateur doit demander un certificat auprès de CN et/ou SAN *\* .base_domain (par exemple, \* .customers.adatum.biz).* Ce certificat peut être utilisé pour authentifier les connexions à plusieurs locataires servis à partir d’un même SBC.


Le tableau suivant est un exemple de configuration.


|Nouveau nom de domaine |Type|Inscrit  |Certificat CN/SAN pour SBC  |Domaine par défaut du client dans l’exemple  |Nom de domaine complet que SBC doit présenter dans l’en-tête du contact lors de l’envoi d’appels à des utilisateurs|
|---------|---------|---------|---------|---------|---------|
|customers.adatum.biz|    Base     |     Dans le client de l’opérateur  |    \*.customers.adatum.biz  |   adatum.biz      |NA, il s’agit d’un client de service, aucun utilisateur |
|sbc1.customers.adatum.biz|    Sous-domaine  |    Dans un client  |    \*.customers.adatum.biz  | woodgrovebank.us  |  sbc1.customers.adatum.biz|
|sbc2.customers.adatum.biz  |   Sous-domaine | Dans un client   |   \*.customers.adatum.biz   |contoso.com   |sbc2.customers.adatum.biz |
|sbc3.customers.adatum.biz |   Sous-domaine | Dans un client |   \*.customers.adatum.biz  |  adventureworks.com | sbc3.customers.adatum.biz |
||         |         |         |         |         |

Pour configurer la base et les sous-domaine, suivez les étapes décrites ci-dessous. Dans l’exemple, nous allons configurer un nom de domaine de base (customers.adatum.biz) et un sous-domaine pour un client (sbc1.customers.adatum.biz dans le client Woodgrove Bank).

> [!NOTE]
> Utilisez sbcX.customers.adatum.biz pour activer la voix dans le client de l’opérateur. sbcX peut être n’importe quel nom d’hôte alphanumérique unique et valide.

## <a name="register-a-base-domain-name-in-the-carrier-tenant"></a>Enregistrer un nom de domaine de base dans le client de l’opérateur

**Ces actions sont effectuées dans le client de l’opérateur.**

### <a name="ensure-that-you-have-appropriate-rights-in-the-carrier-tenant"></a>Vérifier que vous avez les droits appropriés dans le client de l’opérateur

Vous ne pouvez ajouter des domaines que si vous vous êtes inscrit au Centre d’administration Microsoft 365 en tant qu’administrateur général. 

Pour valider votre rôle, connectez-vous au Centre d’administration Microsoft 365 ( , allez à Utilisateurs actifs utilisateurs, puis vérifiez que vous avez un rôle Administrateur https://portal.office.com)   >  général. 

Pour plus d’informations sur les rôles d’administrateur et la manière d’attribuer un rôle dans Microsoft 365 ou Office 365 rôles, voir À propos des [rôles d’administrateur.](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)

### <a name="add-a-base-domain-to-the-tenant-and-verify-it"></a>Ajouter un domaine de base au client et le vérifier

1. Dans le Centre d’administration Microsoft 365, allez à **Configurer**  >  **les domaines** Ajouter un  >  **domaine.**
2. Dans la **zone Entrer un domaine dont vous êtes** propriétaire, tapez le nom de domaine (FQDN) du domaine de base. Dans l’exemple suivant, le domaine de base est *customers.adatum.biz.*

    ![Capture d’écran montrant la page Ajouter un domaine](media/direct-routing-2-sbc-add-domain.png)

3. Cliquez sur **Suivant**.
4. Dans l’exemple, le client a déjà adatum.biz nom de domaine vérifié. L’Assistant ne demande pas de vérification supplémentaire, customers.adatum.biz est un sous-domaine du nom déjà enregistré. Toutefois, si vous ajoutez un FQDN qui n’a pas été vérifié auparavant, vous devrez passer par le processus de vérification. Le processus de vérification est décrit [ci-dessous.](#add-a-subdomain-to-the-customer-tenant-and-verify-it)

    ![Capture d’écran montrant la confirmation d’un nom de domaine vérifié](media/direct-routing-3-sbc-verify-domain.png)

5. Cliquez **sur Suivant,** puis sur la page Mettre Paramètres **DNS** à jour, je sélectionne J’ajoute les enregistrements **DNS** moi-même, puis je clique sur **Suivant.**
6. Dans la page suivante, effacer toutes les valeurs (sauf si vous voulez utiliser le nom de domaine pour Exchange, SharePoint ou Teams/Skype Entreprise), cliquez sur **Suivant,** puis sur **Terminer.** Assurez-vous que votre nouveau domaine est dans l’état final du programme d’installation.

    ![Capture d’écran montrant les domaines dont l’état est terminé](media/direct-routing-14-sbc-setup-complete.png)

### <a name="activate-the-domain-name"></a>Activer le nom de domaine

Une fois que vous avez enregistré un nom de domaine, vous devez l’activer en ajoutant au moins un utilisateur avec une licence Système téléphonique et en attribuant une adresse SIP avec la partie FQDN de l’adresse SIP correspondant au domaine de base créé. La licence peut être révoquée après l’activation du domaine (cela peut prendre jusqu’à 24 heures).

> [!NOTE]
> Le client de l’opérateur doit conserver au moins Système téléphonique licence attribuée au client pour éviter la suppression de la configuration Skype Entreprise client. 

*Pour plus [d’informations](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) sur l’ajout d’utilisateurs Microsoft 365 ou Office 365 organisation, consultez l’aide Microsoft 365 domaines Office 365 domaine.*

Par exemple : test@customers.adatum.biz

![Capture d’écran de la page d’activation du domaine de base](media/direct-routing-4-sbc-domain-activation.png)

## <a name="register-a-subdomain-name-in-a-customer-tenant"></a>Enregistrer un nom de sous-domaine dans un client

Vous devrez créer un nom de sous-domaine unique pour chaque client. Dans cet exemple, nous allons créer un sous-domaine sbc1.customers.adatum.biz client avec le nom de domaine par défaut woodgrovebank.us.

**Toutes les actions ci-dessous sont dans le client client.**

### <a name="ensure-that-you-have-appropriate-rights-in-the-customer-tenant"></a>Vérifier que vous avez les droits appropriés dans le client

Vous ne pouvez ajouter des domaines que si vous vous êtes inscrit au Centre d’administration Microsoft 365 en tant qu’administrateur général. 

Pour valider votre rôle, connectez-vous au Centre d’administration Microsoft 365 ( , allez à Utilisateurs actifs utilisateurs, puis vérifiez que vous avez un rôle Administrateur https://portal.office.com)   >  général. 

Pour plus d’informations sur les rôles d’administrateur et la manière d’attribuer un rôle dans Microsoft 365 ou Office 365 rôles, voir À propos des [rôles d’administrateur.](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)

### <a name="add-a-subdomain-to-the-customer-tenant-and-verify-it"></a>Ajouter un sous-domaine au client et le vérifier
1. Dans le Centre d’administration Microsoft 365, allez à **Configurer**  >  **les domaines** Ajouter un  >  **domaine.**
2. Dans la **zone Entrer un domaine dont vous êtes** propriétaire, tapez le nom de domaine (FQDN) du sous-domaine de ce client. Dans l’exemple ci-dessous, le sous-domaine est sbc1.customers.adatum.biz.

    ![Capture d’écran de la page Ajouter un domaine](media/direct-routing-5-sbc-add-customer-domain.png)

3. Cliquez sur **Suivant**.
4. Le FQDN n’a jamais été enregistré dans le client. Dans l’étape suivante, vous devrez vérifier le domaine. Sélectionnez **Ajouter un enregistrement TXT à la place.** 

    ![Capture d’écran de la page Vérifier le domaine](media/direct-routing-6-sbc-verify-customer-domain.png)

5. Cliquez **sur** Suivant, puis notez la valeur TXT générée pour vérifier le nom de domaine.

    ![Capture d’écran d’enregistrements texte dans la page Vérifier le domaine](media/direct-routing-7-sbc-verify-domain-txt.png)

6. Créez l’enregistrement TXT avec la valeur de l’étape précédente du fournisseur d’hébergement DNS de l’opérateur.

    ![Capture d’écran montrant la création de l’enregistrement TXT](media/direct-routing-8-sbc-txt-record.png)

    Pour plus d’informations, voir Créer des enregistrements [DNS chez n’importe quel fournisseur d’hébergement DNS.](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166)

7. Revenir à la base de données du Centre d’administration Microsoft 365 et cliquer sur **Vérifier.** 
8. Sur la page suivante, **sélectionnez J’ajoute** les enregistrements DNS moi-même, puis je clique **sur Suivant.**

    ![Capture d’écran des options dans la page Mettre à jour les paramètres DNS](media/direct-routing-9-sbc-update-dns.png)

9. Dans la page **Choisir vos services en ligne,** effacer toutes les options et cliquer sur **Suivant.**

    ![Capture d’écran de la page Choisir vos services en ligne](media/direct-routing-10-sbc-choose-services.png)

10. Cliquez **sur Terminer** dans la page Mettre à jour les **paramètres DNS.**

    ![Capture d’écran de la page Mettre à jour les paramètres DNS](media/direct-routing-11-sbc-update-dns-finish.png)

11. Assurez-vous que l’état **est terminé.** 
    
    ![Capture d’écran de la page montrant l’état du programme d’installation terminé](media/direct-routing-12-sbc-setup-complete.png)
    
> [!NOTE]
> L’URL de base et le sous-domaine du client doivent se trouver sur le même client pour pouvoir ajouter une ligne _d’itinéraire_ directe.

### <a name="activate-the-subdomain-name"></a>Activer le nom du sous-domaine

Après avoir enregistré un nom de domaine, vous devez l’activer en ajoutant au moins un utilisateur et en attribuant une adresse SIP avec la partie de nom de domaine complet de l’adresse SIP correspondant au sous-domaine créé dans le client. La licence peut être révoquée de l’utilisateur après l’activation du sous-domaine (l’activation peut prendre jusqu’à 24 heures).

*Pour plus [d’informations](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) sur l’ajout d’utilisateurs Microsoft 365 ou Office 365 organisation, consultez l’aide Microsoft 365 domaines Office 365 domaine.*

Par exemple : test@sbc1.customers.adatum.biz

![Capture d’écran de la page Activation de la sous-domaine](media/direct-routing-13-sbc-activate-subdomain.png)

### <a name="create-a-trunk-and-provision-users"></a>Créer une ligne et mettre en service des utilisateurs

Avec la version initiale du routage direct, Microsoft a demandé qu’une ligne soit ajoutée à chaque client servi (client) à l’aide de New-CSOnlinePSTNGateway.

Cela n’est toutefois pas optimal pour deux raisons :
 
- **Gestion des frais.** Par exemple, le rechargement ou le dé déchargement d’un SBC modifie certains paramètres, comme l’activation ou la désactivation de la dérivation média. La modification du port nécessite la modification des paramètres de plusieurs locataires (en exécutant Set-CSOnlinePSTNGateway), mais il s’agit en fait du même SBC. 

-  **Traitement des frais.** Collecte et surveillance des données d’intégrité de ligne - Les options SIP collectées à partir de plusieurs ligne logiques qui sont en réalité le même SBC et la même ligne physique ralentissent le traitement des données de routage.
 
Sur la base de ces commentaires, Microsoft apporte une nouvelle logique de mise en service des ligne pour les clients clients.

Deux nouvelles entités ont été introduites :
-    Ligne d’opérateur enregistrée dans le client de l’opérateur à l’aide de la commande New-CSOnlinePSTNGateway, par exemple New-CSOnlinePSTNGateway -FQDN customers.adatum.biz -SIPSignalingport 5068 -ForwardPAI $true.

-    Ligne dérivée qui ne nécessite pas d’inscription. Il s’agit simplement d’un nom d’hôte souhaité ajouté à partir de la ligne de l’opérateur. Il dérive tous ses paramètres de configuration de la ligne de l’opérateur. Il n’est pas nécessaire de créer la ligne dérivée dans PowerShell, et l’association avec la ligne de l’opérateur est basée sur le nom de nom de domaine complet (voir les détails ci-dessous).

**Logique d’approvisionnement et exemple**

-    Les opérateurs ont seulement besoin de configurer et de gérer une seule ligne (ligne d’opérateur dans le domaine de l’opérateur), à l’aide de Set-CSOnlinePSTNGateway ligne. Dans l’exemple ci-dessus, il est adatum.biz ;
-    Dans le client client, l’opérateur doit uniquement ajouter le nom de fQDN de ligne dérivée aux stratégies de routage voix des utilisateurs. Il n’est pas nécessaire d’exécuter New-CSOnlinePSTNGateway une ligne.
-    La ligne dérivée, comme son nom le suggère, hérite ou dérive tous les paramètres de configuration de la ligne d’opérateur. Exemples :
-    Customers.adatum.biz ligne d’opérateur qui doit être créée dans le client de l’opérateur.
-    Sbc1.customers.adatum.biz ligne dérivée dans un client client qui n’a pas besoin d’être créée dans PowerShell.  Vous pouvez simplement ajouter le nom de la ligne dérivée dans le client client dans la stratégie de routage voix en ligne sans la créer.
-   Carrier devra configurer l’enregistrement DNS résolvant le nom de fQDN de ligne dérivée à l’adresse ip de l’opérateur SBC.

-    Toutes les modifications apportées à une ligne d’opérateur (sur le client de l’opérateur) sont automatiquement appliquées aux ligne dérivées. Par exemple, les opérateurs peuvent modifier un port SIP sur la ligne du transporteur, et ce changement s’applique à toutes les ligne dérivées. Une nouvelle logique de configuration des ligne simplifie la gestion, car vous n’avez pas besoin d’aller à chaque client et de modifier le paramètre sur chaque ligne.
-    Les options sont envoyées uniquement à la ligne d’opérateur FQDN. L’état d’état de la ligne du transporteur est appliqué à toutes les ligne dérivées et est utilisé pour les décisions de routage. En savoir plus sur [les options de routage direct.](./direct-routing-monitor-and-troubleshoot.md)
-    L’opérateur peut utiliser la ligne d’opérateur, et toutes les branches dérivées sont également désoutoutées. 
 
> [!NOTE]
> Les règles de traduction des nombres appliquées sur la ligne du transporteur ne s’appliquent pas aux ligne dérivées. Il s’agit d’un problème connu. Une autre solution consiste à créer une règle de traduction des nombres pour le client de chaque client.

**Migration du modèle précédent vers la ligne du transporteur**
 
Pour la migration de l’implémentation actuelle du modèle hébergé par l’opérateur vers le nouveau modèle, les opérateurs doivent reconfigurer les ligne pour les clients client. Supprimez les ligne des clients client à l’aide de Remove-CSOnlinePSTNGateway (en laissant la ligne dans le client de l’opérateur) -

Nous encourageons vivement la migration vers la nouvelle solution dès que possible, car nous améliorerons la surveillance et l’approvisionnement à l’aide de l’opérateur et du modèle de ligne dérivée.
 

Reportez-vous aux [instructions du](#deploy-and-configure-the-sbc) fournisseur SBC sur la configuration de l’envoi du nom de domaine complet (FQDN) des sous-domaine dans l’en-tête contact.

## <a name="considerations-for-setting-up-muti-tenant-failover"></a>Considérations pour la configuration duover muti-client 

Pour configurer leover pour un environnement multi-client, vous devez faire les choses suivantes :

- Pour chaque client, ajoutez les FQDN pour deux SBCs différents.  Par exemple :

   customer1.sbc1.contoso.com <br>
   customer1.sbc2.contoso.com <br>

- Dans les stratégies de routage voix en ligne des utilisateurs, spécifiez les deux SBCs.  En cas d’échec d’un SBC, la stratégie de routage route les appels vers le deuxième SBC.


## <a name="see-also"></a>Voir aussi

[Planifier le routage direct](direct-routing-plan.md)

[Configurer le routage direct](direct-routing-configure.md)
