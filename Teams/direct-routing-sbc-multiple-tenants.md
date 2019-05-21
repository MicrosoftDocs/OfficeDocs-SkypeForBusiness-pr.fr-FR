---
title: Configurer un contrôleur de frontière de session pour plusieurs clients
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
- Teams_ITAdmin_Help
- M365-voice
appliesto:
- Microsoft Teams
description: Apprenez à configurer un contrôleur de bordure de session (SBC) pour servir plusieurs clients.
ms.openlocfilehash: 5392359307d97e010f86d3bb71f2f7c3f3d1ffb6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34290468"
---
# <a name="configure-a-session-border-controller-for-multiple-tenants"></a>Configurer un contrôleur de frontière de session pour plusieurs clients

Le routage direct prend en charge la configuration d’un contrôleur de bordure de session (SBC) pour servir plusieurs clients.

> [!NOTE]
> Ce scénario est destiné aux partenaires Microsoft et/ou aux opérateurs RTC, désignés sous le nom de opérateurs plus loin dans ce document. Un opérateur vend aux utilisateurs de services de téléphonie remis à Microsoft Teams. 

Opérateur:
- Déploie et gère une SBC sur son centre de donnes (les clients n’ont pas besoin d’implémenter de SBC et ils reçoivent les services de téléphonie de l’opérateur dans le client Teams).
- Interconnecte l’SBC à plusieurs clients.
- Fournit des services RTC aux clients.
- Gère la fin de la qualité des appels.
- Frais pour les services RTC séparément.

Microsoft ne gère pas les opérateurs. Microsoft propose un système PBX (Microsoft Phone System) et un client Teams, certifie les téléphones et certifie SBCs qui peut être utilisé avec le système Microsoft Phone. Avant de choisir un opérateur, assurez-vous que votre choix dispose d’une SBC certifié et peut gérer la fin de la qualité de la voix.

Vous trouverez ci-après les étapes d’implémentation techniques de la configuration du scénario.

**Opérateur uniquement:**
1. Déployez le SBC et configurez-le pour le scénario d’hébergement conformément aux [instructions des fournisseurs de SBC certifiés](#deploy-and-configure-the-sbc).
2. Enregistrez un nom de domaine de base dans le client de l’opérateur et demandez un certificat générique.
3. Enregistrez un sous-domaine pour chaque client, qui fait partie du domaine de base.

**Opérateur avec un administrateur global du client:**
1. Ajoutez le nom de sous-domaine au locataire du client.
2. Activez le nom de sous-domaine.
3. Configurez le Trunk du transporteur sur le locataire du client et approvisionnez les utilisateurs.

*Veuillez vous assurer que vous comprenez les concepts de base de l’utilisation de la gestion des enregistrements DNS et comment le nom de domaine est géré dans Office 365. Consultez [obtenir de l’aide sur les domaines Office 365 avant de](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) continuer.*

## <a name="deploy-and-configure-the-sbc"></a>Déploiement et configuration de l’SBC

Pour plus d’informations sur le déploiement et la configuration de SBCs pour un scénario d’hébergement SBC, consultez la documentation du fournisseur de SBC.

- **AudioCodes:** [Remarques sur la configuration du routage direct](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-Microsoft-Teams), la configuration du scénario d’hébergement SBC décrit dans «connexion de AudioCodes SBC à la configuration de modèle d’hébergement de Microsoft teams 
- **Communications du ruban:**  Reportez-vous au [Guide de configuration de Microsoft teams SBC principal du ruban](https://support.sonus.net/display/IOT/PBXs+-+SBC+5k7kSWe) pour obtenir une documentation sur la configuration de la série de cœurs du ruban SBCS et sur cette page. [ Bordure](https://support.sonus.net/display/UXDOC70/Best+Practice+-+Configuring+Carriers+for+Microsoft+Teams+Direct+Routing)

> [!NOTE]
> Veuillez nous concentrer sur la configuration de l’en-tête «contact». L’en-tête contact permet de rechercher le locataire du client dans le message d’invitation entrant. 

## <a name="register-a-base-domain-and-subdomains"></a>Inscrire un domaine de base et des sous-domaines

Pour le scénario d’hébergement, vous devez créer:
- Un nom de domaine de base possédé par l’opérateur.
- Sous-domaine qui fait partie du nom de domaine de base dans chaque client de client.

Dans l’exemple suivant:
- Adatum est un opérateur qui dessert plusieurs clients en fournissant des services Internet et de téléphonie.
- Woodgrove Bank, contoso et Adventure Works sont trois clients possédant des domaines Office 365, mais ils reçoivent les services de téléphonie de adatum.

Les sous-domaines **doivent** correspondre au nom de domaine complet (FQDN) du Trunk qui sera configuré pour le client et du nom de domaine complet (FQDN) dans l’en-tête de contact lors de l’envoi de l’invitation à Office 365. 

Lorsqu’un appel arrive sur l’interface de routage directe d’Office 365, l’interface utilise l’en-tête de contact pour trouver le client à l’endroit où l’utilisateur doit être recherché. Le routage direct n’utilise pas la recherche de numéros de téléphone dans l’invitation, car certains clients peuvent avoir des numéros qui peuvent se chevaucher dans plusieurs clients. Par conséquent, le nom de domaine complet dans l’en-tête de contact est requis pour identifier le client exact pour trouver le numéro de téléphone de l’utilisateur.

*Pour plus d’informations sur la création de noms de domaine dans les clients Office 365, voir [obtenir de l’aide sur les domaines office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) .*

Le diagramme suivant récapitule les exigences relatives aux domaines de base, sous-domaines et en-tête de contact.

![Exigences en matière de domaine de base, de sous-domaines et d’en-tête de contact](media/direct-routing-1-sbc-requirements.png)

L’SBC nécessite un certificat pour authentifier les connexions. Pour le scénario d’hébergement SBC, l’opérateur doit demander un certificat avec San * \*. base_domain (par exemple, \*Customers.adatum.biz)*. Ce certificat peut être utilisé pour authentifier les connexions à plusieurs clients desservis à partir d’un SBC unique.

Le tableau suivant illustre une configuration.


|Nouveau nom de domaine |Type|Enregistrement  |Certificat SAN pour SBC  |Domaine par défaut du client dans l’exemple  |Nom de domaine complet que SBC doit présenter dans l’en-tête de contact lors de l’envoi d’appels aux utilisateurs|
|---------|---------|---------|---------|---------|---------|
|customers.adatum.biz|    Assiette     |     Client du transporteur  |    \*. customers.adatum.biz  |   adatum.biz      |NA, il s’agit d’un client de service, sans utilisateurs. |
|sbc1.customers.adatum.biz|    Sous-domaine  |    Dans un client client  |    \*. customers.adatum.biz  | woodgrovebank.us  |  sbc1.customers.adatum.biz|
|sbc2.customers.adatum.biz  |   Sous-domaine | Dans un client client   |   \*. customers.adatum.biz   |contoso.com   |sbc2.customers.adatum.biz |
|sbc3.customers.adatum.biz |   Sous-domaine | Dans un client client |   \*. customers.adatum.biz  |  adventureworks.com | sbc3.customers.adatum.biz |
||         |         |         |         |         |

Pour configurer la base et les sous-domaines, suivez les étapes décrites ci-dessous. Dans l’exemple, nous allons configurer un nom de domaine de base (customers.adatum.biz) et un sous-domaine pour un client (sbc1.customers.adatum.biz dans le client Woodgrove Bank).

## <a name="register-a-base-domain-name-in-the-carrier-tenant"></a>Inscrire un nom de domaine de base dans le client de l’opérateur

**Ces actions sont exécutées dans le locataire du transporteur.**

### <a name="ensure-that-you-have-appropriate-rights-in-the-carrier-tenant"></a>Vérifiez que vous disposez des droits appropriés pour le locataire du transporteur

Vous pouvez ajouter de nouveaux domaines uniquement si vous vous êtes connecté au centre d’administration Microsoft 365 en tant qu’administrateur général. 

Pour valider le rôle dont vous disposez, connectez-vous au centre d’administration 365 Microsofthttps://portal.office.com)(, accédez à **utilisateurs** > **actifs**, puis vérifiez que vous avez le rôle d’administrateur général. 

Pour plus d’informations sur les rôles d’administrateur et comment attribuer un rôle dans Office 365, voir [à propos des rôles d’administrateur office 365](https://support.office.com/article/About-Office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).

### <a name="add-a-base-domain-to-the-tenant-and-verify-it"></a>Ajouter un domaine de base au client et le vérifier

1.  Dans le centre d’administration Microsoft 365, accédez à **configuration** > des**domaines** > **Ajouter un domaine**.
2.  Dans la zone **Entrez un domaine que vous possédez** , tapez le nom de domaine complet (FQDN) du domaine de base. Dans l’exemple suivant, le domaine de base est *Customers.adatum.biz*.

    ![Ajout d’un domaine de base](media/direct-routing-2-sbc-add-domain.png)

3. Cliquez sur **Suivant**.
4. Dans l’exemple, le locataire a déjà adatum.biz comme nom de domaine vérifié. L’Assistant ne demande pas de vérification supplémentaire, car customers.adatum.biz est un sous-domaine du nom déjà enregistré. Toutefois, si vous ajoutez un nom de domaine complet (FQDN) qui n’a pas été vérifié auparavant, vous devez suivre le processus de vérification. Le processus de vérification est [décrit ci-dessous](#add-a-subdomain-to-the-customer-tenant-and-verify-it).

    ![Confirmation d’un nom de domaine vérifié](media/direct-routing-3-sbc-verify-domain.png)

5.  Cliquez sur **suivant**, puis, dans la page **mettre à jour les paramètres DNS** , sélectionnez **Ajouter les enregistrements DNS moi-même** , puis cliquez sur **suivant**.
6.  Sur la page suivante, effacez toutes les valeurs (sauf si vous souhaitez utiliser le nom de domaine pour Exchange, SharePoint ou teams/Skype entreprise), cliquez sur **suivant**, puis sur **Terminer**. Assurez-vous que votre nouveau domaine est dans l’État configuration terminée.

    ![Domaines affichant l’état d’achèvement de l’installation](media/direct-routing-14-sbc-setup-complete.png)

### <a name="activate-the-domain-name"></a>Activer le nom de domaine

Après avoir enregistré un nom de domaine, vous devez l’activer en ajoutant au moins une licence E1, E3 ou E5 et en attribuant une adresse SIP à la partie FQDN de l’adresse SIP correspondant au domaine de base créé. 

*Pour plus d’informations sur l’ajout d’utilisateurs dans les clients Office 365, voir [obtenir de l’aide sur les domaines office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) .*

Par exemple: test@customers.adatum.biz

![Page activation du domaine de base](media/direct-routing-4-sbc-domain-activation.png)

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

    ![Ajouter un sous-domaine de client](media/direct-routing-5-sbc-add-customer-domain.png)

3. Cliquez sur **Suivant**.
4. Le nom de domaine complet ne s’est jamais inscrit dans le client. À l’étape suivante, vous devrez vérifier le domaine. À **la place, sélectionnez Ajouter un enregistrement txt**. 

    ![Options de la page vérifier le domaine](media/direct-routing-6-sbc-verify-customer-domain.png)

5. Cliquez sur **suivant**, puis notez la valeur txt générée pour vérifier le nom de domaine.

    ![Enregistrements de texte dans la page vérifier le domaine](media/direct-routing-7-sbc-verify-domain-txt.png)

6. Créez l’enregistrement TXT avec la valeur de l’étape précédente du fournisseur d’hébergement DNS de l’opérateur.

    ![Création de l’enregistrement TXT dans le fournisseur d’hébergement DNS de l’opérateur](media/direct-routing-8-sbc-txt-record.png)

    Pour plus d’informations, voir [créer des enregistrements DNS auprès d’un fournisseur d’hébergement DNS pour Office 365](https://support.office.com/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166).

7. Revenez au centre d’administration 365 Microsoft et cliquez sur **vérifier**. 
8. Sur la page suivante, sélectionnez **je vais ajouter les enregistrements DNS moi-même** , puis cliquez sur **suivant**.

    ![Options de la page mettre à jour les paramètres DNS](media/direct-routing-9-sbc-update-dns.png)

9. Dans la page **choisir vos services en ligne** , désactivez toutes les options, puis cliquez sur **suivant**.

    ![La page choisir vos services en ligne](media/direct-routing-10-sbc-choose-services.png)

10. Cliquez sur **Terminer** dans la page **mettre à jour les paramètres DNS** .

    ![Page mettre à jour les paramètres DNS](media/direct-routing-11-sbc-update-dns-finish.png)

11. Assurez-vous que le paramètre statut est **terminé**. 
    
    ![Page indiquant l’état d’achèvement de l’installation](media/direct-routing-12-sbc-setup-complete.png)

### <a name="activate-the-subdomain-name"></a>Activer le nom de sous-domaine

Après avoir enregistré un nom de domaine, vous devez l’activer en ajoutant au moins un utilisateur et en assignant une adresse SIP avec la partie FQDN de l’adresse SIP correspondant au sous-domaine créé dans le client client.

*Pour plus d’informations sur l’ajout d’utilisateurs dans les clients Office 365, voir [obtenir de l’aide sur les domaines office 365](https://support.office.com/article/Get-help-with-Office-365-domains-28343f3a-dcee-41b6-9b97-5b0f4999b7ef) .*

Par exemple: test@sbc1.customers.adatum.biz

![Activation de la page de sous-domaine](media/direct-routing-13-sbc-activate-subdomain.png)

### <a name="create-a-trunk-and-provision-users"></a>Créer un Trunking et configurer les utilisateurs

> [!NOTE]
> En fonction de votre avis que nous avons reçu dans le programme d’adoption technique, Microsoft peut changer le processus de création de Trunks dans les clients clients pour simplifier le processus. Pour plus d’informations, consultez les mises à jour de la documentation sur cette page et suivez les blogs de la communauté technique Microsoft. 

Créez un Trunk dans le domaine du client à l’aide de la commande New-CSonlinePSTNGateway. Le nom de domaine complet du Trunk **doit** correspondre au sous-domaine créé pour le client.

Par exemple :

```
New-CSOnlinePSTNGateway –FQDN sbc1.customers.adatum.biz -SipSignallingPort 5068
```

Lors de la création du Trunk, vous pouvez recevoir le message d’erreur suivant:

```
Can not use the "sbc1.customers.adatum.biz" domain as it was not configured for this tenant.
```

Veuillez patienter pendant que l’inscription et l’activation du domaine sont répliquées, puis réessayez.

Approvisionner les utilisateurs avec les numéros de téléphone et configurer le routage de la voix.

Pour plus d’informations sur le nouveau-CSOnlinePSTNGateway, la mise en service des utilisateurs et la configuration du routage des communications vocales, consultez [configurer le routage direct](direct-routing-configure.md).


Pour plus d’informations, reportez-vous à la rubrique [instructions du fournisseur SBC](#deploy-and-configure-the-sbc) sur la configuration de l’envoi du nom FQDN des sous-domaines dans l’en-tête contact.

