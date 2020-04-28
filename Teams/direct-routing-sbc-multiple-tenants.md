---
title: Configurer le contrôleur de bordure de session-plusieurs clients
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
description: Apprenez à configurer un contrôleur de bordure de session (SBC) pour servir plusieurs clients pour les partenaires Microsoft et/ou les opérateurs PSTN.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 061d0afec96e6c76e49f6471ea8ed2f673e33eba
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43901849"
---
# <a name="configure-a-session-border-controller-for-multiple-tenants"></a>Configurer un contrôleur de frontière de session pour plusieurs clients

Le routage direct prend en charge la configuration d’un contrôleur de bordure de session (SBC) pour servir plusieurs clients.

> [!NOTE]
> Ce scénario est destiné aux partenaires Microsoft et/ou aux opérateurs RTC, désignés sous le nom de opérateurs plus loin dans ce document. Un opérateur vend aux utilisateurs de services de téléphonie remis à Microsoft Teams. 

Opérateur :
- Déploie et gère une SBC sur son centre de donnes (les clients n’ont pas besoin d’implémenter de SBC et ils reçoivent les services de téléphonie de l’opérateur dans le client Teams).
- Interconnecte l’SBC à plusieurs clients.
- Fournit des services RTC aux clients.
- Gère la fin de la qualité des appels.
- Frais pour les services RTC séparément.

Microsoft ne gère pas les opérateurs. Microsoft propose une offre PBX (système Microsoft Phone) et un client Teams. Microsoft certifie également des téléphones et certifie les SBCs qui peuvent être utilisés avec le système Microsoft Phone. Avant de choisir un opérateur, assurez-vous que votre choix dispose d’une SBC certifié et peut gérer la fin de la qualité de la voix.

Vous trouverez ci-après les étapes d’implémentation techniques de la configuration du scénario.

**Opérateur uniquement :**
1. Déployez le SBC et configurez-le pour le scénario d’hébergement conformément aux [instructions des fournisseurs de SBC certifiés](#deploy-and-configure-the-sbc).
2. Enregistrez un nom de domaine de base dans le client de l’opérateur et demandez un certificat générique.
3. Enregistrez un sous-domaine pour chaque client, qui fait partie du domaine de base.

**Opérateur avec un administrateur global du client :**
1. Ajoutez le nom de sous-domaine au locataire du client.
2. Activez le nom de sous-domaine.
3. Configurez le Trunk du transporteur sur le locataire du client et approvisionnez les utilisateurs.

*Veuillez vous assurer que vous comprenez les concepts de base de l’utilisation de la gestion des enregistrements DNS et comment le nom de domaine est géré dans Office 365. Consultez [obtenir de l’aide sur les domaines Office 365 avant de](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) continuer.*

## <a name="deploy-and-configure-the-sbc"></a>Déploiement et configuration de l’SBC

Pour plus d’informations sur le déploiement et la configuration de SBCs pour un scénario d’hébergement SBC, consultez la documentation du fournisseur de SBC.

- **AudioCodes :** [notes de configuration de routage direct](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams), la configuration du scénario d’hébergement SBC décrite dans «connexion de AudioCodes SBC à la configuration de modèle d’hébergement de Microsoft teams 
- **Oracle :** [notes de configuration de routage direct](https://www.oracle.com/technetwork/indexes/documentation/acme-packet-2228107.html), la configuration du scénario d’hébergement SBC est décrite dans la section « Microsoft ». 
- **Communications du ruban :**  Pour plus d’informations sur la configuration du ruban de base du ruban, voir le [Guide de configuration de Microsoft teams](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe) (en anglais [)](https://support.sonus.net/display/UXDOC70/Best+Practice+-+Configuring+Carriers+for+Microsoft+Teams+Direct+Routing) sur la configuration de l’interface du ruban de Microsoft Teams, reportez-vous à la rubrique recommandations pour le routage
- **Te-systèmes (anynode) :**  Inscrivez-vous sur la page de la [communauté te-systèmes](https://community.te-systems.de/) pour obtenir de la documentation et des exemples sur la configuration de anynode SBC pour plusieurs clients.

> [!NOTE]
> Veuillez nous concentrer sur la configuration de l’en-tête « contact ». L’en-tête contact permet de rechercher le locataire du client dans le message d’invitation entrant. 

## <a name="register-a-base-domain-and-subdomains"></a>Inscrire un domaine de base et des sous-domaines

Pour le scénario d’hébergement, vous devez créer :
- Un nom de domaine de base possédé par l’opérateur.
- Sous-domaine qui fait partie du nom de domaine de base dans chaque client de client.

Dans l’exemple suivant :
- Adatum est un opérateur qui dessert plusieurs clients en fournissant des services Internet et de téléphonie.
- Woodgrove Bank, contoso et Adventure Works sont trois clients possédant des domaines Office 365, mais ils reçoivent les services de téléphonie de adatum.

Les sous-domaines **doivent** correspondre au nom de domaine complet (FQDN) du Trunk qui sera configuré pour le client et du nom de domaine complet (FQDN) dans l’en-tête de contact lors de l’envoi de l’invitation à Office 365. 

Lorsqu’un appel arrive sur l’interface de routage directe d’Office 365, l’interface utilise l’en-tête de contact pour trouver le client à l’endroit où l’utilisateur doit être recherché. Le routage direct n’utilise pas la recherche de numéros de téléphone dans l’invitation, car certains clients peuvent avoir des numéros qui peuvent se chevaucher dans plusieurs clients. Par conséquent, le nom de domaine complet dans l’en-tête de contact est requis pour identifier le client exact pour trouver le numéro de téléphone de l’utilisateur.

*Pour plus d’informations sur la création de noms de domaine dans les organisations Office 365, voir [obtenir de l’aide sur les domaines office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) .*

Le diagramme suivant récapitule les exigences relatives aux domaines de base, sous-domaines et en-tête de contact.

![Diagramme présentant les exigences relatives aux domaines et en-tête de contact](media/direct-routing-1-sbc-requirements.png)

L’SBC nécessite un certificat pour authentifier les connexions. Pour le scénario d’hébergement SBC, l’opérateur doit demander un certificat avec le San * \*. base_domain (par exemple \*,. Customers.adatum.biz)*. Ce certificat peut être utilisé pour authentifier les connexions à plusieurs clients desservis à partir d’un SBC unique.


Le tableau suivant illustre une configuration.


|Nouveau nom de domaine |Type|Enregistrement  |Certificat SAN pour SBC  |Domaine par défaut du client dans l’exemple  |Nom de domaine complet que SBC doit présenter dans l’en-tête de contact lors de l’envoi d’appels aux utilisateurs|
|---------|---------|---------|---------|---------|---------|
|customers.adatum.biz|    Assiette     |     Client du transporteur  |    \*. customers.adatum.biz  |   adatum.biz      |NA, il s’agit d’un client de service, sans utilisateurs. |
|sbc1.customers.adatum.biz|    Sous-domaine  |    Dans un client client  |    \*. customers.adatum.biz  | woodgrovebank.us  |  sbc1.customers.adatum.biz|
|sbc2.customers.adatum.biz  |   Sous-domaine | Dans un client client   |   \*. customers.adatum.biz   |contoso.com   |sbc2.customers.adatum.biz |
|sbc3.customers.adatum.biz |   Sous-domaine | Dans un client client |   \*. customers.adatum.biz  |  adventureworks.com | sbc3.customers.adatum.biz |
||         |         |         |         |         |

Pour configurer la base et les sous-domaines, suivez les étapes décrites ci-dessous. Dans l’exemple, nous allons configurer un nom de domaine de base (customers.adatum.biz) et un sous-domaine pour un client (sbc1.customers.adatum.biz dans le client Woodgrove Bank).

> [!NOTE]
> Utilisez sbcX.customers.adatum.biz pour activer la voix dans le locataire du transporteur.

## <a name="register-a-base-domain-name-in-the-carrier-tenant"></a>Inscrire un nom de domaine de base dans le client de l’opérateur

**Ces actions sont exécutées dans le locataire du transporteur.**

### <a name="ensure-that-you-have-appropriate-rights-in-the-carrier-tenant"></a>Vérifiez que vous disposez des droits appropriés pour le locataire du transporteur

Vous pouvez ajouter de nouveaux domaines uniquement si vous vous êtes connecté au centre d’administration Microsoft 365 en tant qu’administrateur général. 

Pour valider le rôle dont vous disposez, connectez-vous au centre d’administration 365 Microsofthttps://portal.office.com)(, accédez à **utilisateurs** > **actifs**, puis vérifiez que vous avez le rôle d’administrateur général. 

Pour plus d’informations sur les rôles d’administrateur et comment attribuer un rôle dans Office 365, voir [à propos des rôles d’administrateur office 365](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).

### <a name="add-a-base-domain-to-the-tenant-and-verify-it"></a>Ajouter un domaine de base au client et le vérifier

1.    Dans le centre d’administration Microsoft 365, accédez à **configuration** > des**domaines** > **Ajouter un domaine**.
2.    Dans la zone **Entrez un domaine que vous possédez** , tapez le nom de domaine complet (FQDN) du domaine de base. Dans l’exemple suivant, le domaine de base est *Customers.adatum.biz*.

    ![Capture d’écran montrant la page Ajouter un domaine](media/direct-routing-2-sbc-add-domain.png)

3. Cliquez sur **Suivant**.
4. Dans l’exemple, le locataire a déjà adatum.biz comme nom de domaine vérifié. L’Assistant ne demande pas de vérification supplémentaire, car customers.adatum.biz est un sous-domaine du nom déjà enregistré. Toutefois, si vous ajoutez un nom de domaine complet (FQDN) qui n’a pas été vérifié auparavant, vous devez suivre le processus de vérification. Le processus de vérification est [décrit ci-dessous](#add-a-subdomain-to-the-customer-tenant-and-verify-it).

    ![Capture d’écran montrant la confirmation d’un nom de domaine vérifié](media/direct-routing-3-sbc-verify-domain.png)

5.    Cliquez sur **suivant**, puis, dans la page **mettre à jour les paramètres DNS** , sélectionnez **Ajouter les enregistrements DNS moi-même** , puis cliquez sur **suivant**.
6.    Sur la page suivante, effacez toutes les valeurs (sauf si vous souhaitez utiliser le nom de domaine pour Exchange, SharePoint ou teams/Skype entreprise), cliquez sur **suivant**, puis sur **Terminer**. Assurez-vous que votre nouveau domaine est dans l’État configuration terminée.

    ![Capture d’écran montrant les domaines dont l’état d’installation est terminé](media/direct-routing-14-sbc-setup-complete.png)

### <a name="activate-the-domain-name"></a>Activer le nom de domaine

Après avoir enregistré un nom de domaine, vous devez l’activer en ajoutant au moins une licence E1, E3 ou E5 et en attribuant une adresse SIP à la partie FQDN de l’adresse SIP correspondant au domaine de base créé. 

*Pour plus d’informations sur l’ajout d’utilisateurs dans les organisations Office 365, voir [obtenir de l’aide sur les domaines office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) .*

Par exemple : test@customers.adatum.biz

![Capture d’écran de la page d’activation du domaine de base](media/direct-routing-4-sbc-domain-activation.png)

## <a name="register-a-subdomain-name-in-a-customer-tenant"></a>Inscrire un nom de sous-domaine dans un client client

Vous devrez créer un nom de sous-domaine unique pour chaque client. Dans cet exemple, nous allons créer un sous-domaine sbc1.customers.adatum.biz dans un client avec le nom de domaine par défaut woodgrovebank.us.

**Toutes les actions ci-dessous se trouvent dans le locataire du client.**

### <a name="ensure-that-you-have-appropriate-rights-in-the-customer-tenant"></a>Vérifiez que vous disposez des droits appropriés pour le locataire du client.

Vous pouvez ajouter de nouveaux domaines uniquement si vous vous êtes connecté au centre d’administration Microsoft 365 en tant qu’administrateur général. 

Pour valider le rôle dont vous disposez, connectez-vous au centre d’administration 365 Microsofthttps://portal.office.com)(, accédez à **utilisateurs** > **actifs**, puis vérifiez que vous avez le rôle d’administrateur général. 

Pour plus d’informations sur les rôles d’administrateur et comment attribuer un rôle dans Office 365, voir [à propos des rôles d’administrateur office 365](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).

### <a name="add-a-subdomain-to-the-customer-tenant-and-verify-it"></a>Ajouter un sous-domaine au locataire du client et le vérifier
1. Dans le centre d’administration Microsoft 365, accédez à **configuration** > des**domaines** > **Ajouter un domaine**.
2. Dans la zone **Entrez un domaine que vous possédez** , tapez le nom de domaine complet (FQDN) du sous-domaine de ce client. Dans l’exemple ci-dessous, le sous-domaine est sbc1.customers.adatum.biz.

    ![Capture d’écran de la page Ajouter un domaine](media/direct-routing-5-sbc-add-customer-domain.png)

3. Cliquez sur **Suivant**.
4. Le nom de domaine complet ne s’est jamais inscrit dans le client. À l’étape suivante, vous devrez vérifier le domaine. À **la place, sélectionnez Ajouter un enregistrement txt**. 

    ![Capture d’écran de la page vérifier le domaine](media/direct-routing-6-sbc-verify-customer-domain.png)

5. Cliquez sur **suivant**, puis notez la valeur txt générée pour vérifier le nom de domaine.

    ![Capture d’écran d’enregistrements de texte dans la page vérifier le domaine](media/direct-routing-7-sbc-verify-domain-txt.png)

6. Créez l’enregistrement TXT avec la valeur de l’étape précédente du fournisseur d’hébergement DNS de l’opérateur.

    ![Capture d’écran montrant la création de l’enregistrement TXT](media/direct-routing-8-sbc-txt-record.png)

    Pour plus d’informations, voir [créer des enregistrements DNS auprès d’un fournisseur d’hébergement DNS pour Office 365](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166).

7. Revenez au centre d’administration 365 Microsoft et cliquez sur **vérifier**. 
8. Sur la page suivante, sélectionnez **je vais ajouter les enregistrements DNS moi-même** , puis cliquez sur **suivant**.

    ![Capture d’écran des options de la page mettre à jour les paramètres DNS](media/direct-routing-9-sbc-update-dns.png)

9. Dans la page **choisir vos services en ligne** , désactivez toutes les options, puis cliquez sur **suivant**.

    ![Capture d’écran de la page choisir vos services en ligne](media/direct-routing-10-sbc-choose-services.png)

10. Cliquez sur **Terminer** dans la page **mettre à jour les paramètres DNS** .

    ![Capture d’écran de la page de mise à jour des paramètres DNS](media/direct-routing-11-sbc-update-dns-finish.png)

11. Assurez-vous que le paramètre statut est **terminé**. 
    
    ![Capture d’écran de la page indiquant l’état du programme d’installation terminé](media/direct-routing-12-sbc-setup-complete.png)

### <a name="activate-the-subdomain-name"></a>Activer le nom de sous-domaine

Après avoir enregistré un nom de domaine, vous devez l’activer en ajoutant au moins un utilisateur et en assignant une adresse SIP avec la partie FQDN de l’adresse SIP correspondant au sous-domaine créé dans le client client.

*Pour plus d’informations sur l’ajout d’utilisateurs dans les organisations Office 365, voir [obtenir de l’aide sur les domaines office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) .*

Par exemple : test@sbc1.customers.adatum.biz

![Capture d’écran de l’activation de la page de sous-domaine](media/direct-routing-13-sbc-activate-subdomain.png)

### <a name="create-a-trunk-and-provision-users"></a>Créer un Trunking et configurer les utilisateurs

Avec la version initiale du routage direct, Microsoft a demandé qu’un Trunk soit ajouté à chaque client desservi (client) à l’aide de New-CSOnlinePSTNGateway.

Toutefois, cela ne s’est pas avéré optimal pour les deux raisons suivantes :
 
- **Gestion des frais d’administration**. Par exemple, si vous déchargez ou déchargez un SBC, vous modifiez des paramètres, par exemple, en activant ou en désactivant la dérivation multimédia. Le changement de port nécessite la modification des paramètres de plusieurs clients (en exécutant Set-CSOnlinePSTNGateway), mais il est en fait le même SBC. 

-  **Traitement**de la surcharge. Collecte et analyse des données d’intégrité de Trunk-les options SIP collectées à partir de plusieurs trunks logiques qui sont en réalité, le même SBC et le même tronc physique, ralentissent le traitement des données de routage.
 
En fonction de ces commentaires, Microsoft s’est associé à une nouvelle logique de mise en service des Trunks pour les clients de clients.

Deux nouvelles entités ont été introduites :
-    Un Trunk de transporteur enregistré dans le client de l’opérateur à l’aide de la commande New-CSOnlinePSTNGateway, par exemple New-CSOnlinePSTNGateway-FQDN customers.adatum.biz-SIPSignalingport 5068-ForwardPAI $true.

-    Trunk dérivé, qui ne nécessite pas d’inscription. Il s’agit simplement d’un nom d’hôte souhaité ajouté à partir du Trunk du transporteur. Il dérive de tous ses paramètres de configuration du Trunk de l’opérateur. Le Trunk dérivé ne doit pas nécessairement être créé dans PowerShell et l’association avec le Trunk de transporteur est basée sur le nom de domaine complet (voir les détails ci-dessous).

**Exemple de logique de mise en service et d’exemple**

-    Les opérateurs doivent uniquement configurer et gérer un seul Trunk (opérateur Trunk dans le domaine de l’opérateur), à l’aide de la commande Set-CSOnlinePSTNGateway. Dans l’exemple ci-dessus, il s’agit de adatum.biz.
-    Dans le client client, l’opérateur doit uniquement ajouter le nom de domaine complet du Trunk dérivé aux stratégies de routage vocal des utilisateurs. Il n’est pas nécessaire d’exécuter New-CSOnlinePSTNGateway pour un Trunk.
-     Le Trunk dérivé, tel que le nom l’indique, hérite de tous les paramètres de configuration de l’opérateur Trunk. Donnés
-    Customers.adatum.biz : le Trunk du transporteur qui doit être créé dans le client de l’opérateur.
-    Sbc1.customers.adatum.biz : Trunk dérivé dans un client client qui n’a pas besoin d’être créé dans PowerShell.  Vous pouvez simplement ajouter le nom du Trunk dérivé dans le client de client dans la stratégie de routage de la voix en ligne sans le créer.
-   L’opérateur doit configurer l’enregistrement DNS pour la résolution de nom de domaine complet du Trunk dérivé sur l’adresse IP de l’SBC.

-    Les modifications apportées sur un Trunk de transporteur (sur le locataire du transporteur) s’appliquent automatiquement aux troncages dérivés. Par exemple, les opérateurs peuvent modifier un port SIP sur le Trunk du transporteur, et cette modification s’applique à tous les Trunks dérivés. La nouvelle logique de configuration des Trunks simplifie la gestion, car vous n’avez pas besoin d’accéder à chaque client et de changer le paramètre sur chaque Trunk.
-    Les options ne sont envoyées qu’au nom de domaine complet du Trunk du transporteur. L’état d’intégrité du Trunk de transporteur est appliqué à toutes les Trunks dérivées et est utilisé pour les décisions de routage. En savoir plus sur les [options de routage direct](https://docs.microsoft.com/microsoftteams/direct-routing-monitor-and-troubleshoot).
-    Le porteur peut décharger le Trunk du porteur, et tous les Trunks dérivés seront également drainés. 
 

**Migration du modèle précédent vers le Trunk de l’opérateur**
 
Pour effectuer une migration à partir de l’implémentation actuelle du modèle hébergé sur l’opérateur vers le nouveau modèle, les opérateurs doivent reconfigurer les Trunks pour les clients clients. Supprimez les Trunks des clients de clients à l’aide de Remove-CSOnlinePSTNGateway (en laissant le Trunk dans le client de l’opérateur)-

Nous vous encourageons vivement à procéder à une migration vers la nouvelle solution le plus rapidement possible, car nous améliorerons la surveillance et l’approvisionnement en utilisant le porteur et le modèle de Trunk dérivé.
 

Pour plus d’informations, reportez-vous à la rubrique [instructions du fournisseur SBC](#deploy-and-configure-the-sbc) sur la configuration de l’envoi du nom FQDN des sous-domaines dans l’en-tête contact.

## <a name="considerations-for-setting-up-muti-tenant-failover"></a>Remarques sur la configuration du basculement de Muti-locataire 

Pour configurer le basculement dans un environnement multi-locataire, vous devez procéder comme suit :

- Pour chaque client, ajoutez les noms de domaine complets pour deux SBCs différents.  Par exemple :

   customer1.sbc1.contoso.com <br>
   customer2.sbc2.contoso.com <br>

- Dans les stratégies de routage de la voix en ligne des utilisateurs, spécifiez SBCs.  En cas d’échec d’un SBC, la stratégie de routage route les appels vers le second SBC.


## <a name="see-also"></a>Voir aussi

[Planifier le routage direct](direct-routing-plan.md)

[Configurer le routage direct](direct-routing-configure.md)

