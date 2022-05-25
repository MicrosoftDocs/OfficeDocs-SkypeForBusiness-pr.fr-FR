---
title: Déployer Skype Connectivity dans Skype Entreprise Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: fb51860b-6f46-4b71-b8c8-682d0982d36d
description: 'Résumé : Découvrez comment connecter Skype Entreprise Server à Skype consommateur. Également appelée connectivité Skype.'
ms.openlocfilehash: 6e569a52569e72d2fe67bdde786b752834452069
ms.sourcegitcommit: c53c22069b1babce7a2364de631057ff501ca1c0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65671680"
---
# <a name="deploy-skype-connectivity-in-skype-for-business-server"></a>Déployer Skype Connectivity dans Skype Entreprise Server

**Résumé:** Découvrez comment connecter Skype Entreprise Server à Skype consommateur. Également appelée connectivité Skype.
  
Cet article décrit le déploiement de la connectivité Skype.
  
## <a name="skype-connectivity-overview-for-it-professionals"></a>Vue d’ensemble de la connectivité Skype pour les professionnels de l’informatique

Skype Connectivité offre aux utilisateurs Skype Entreprise la possibilité de rechercher et d’ajouter des utilisateurs Skype. Skype Connectivité est une fonctionnalité de Skype Entreprise qui vous permet d’activer la fédération et la recherche d’annuaires avec Skype utilisateurs. Une fois que vous avez activé Skype Connectivité, vos utilisateurs Skype Entreprise pourront rechercher et ajouter Skype utilisateurs.
  
## <a name="skype-directory-search"></a>recherche d’annuaire Skype

Skype fonctionnalité de recherche d’annuaire offre aux utilisateurs Skype Entreprise la possibilité de rechercher des contacts Skype. La fonctionnalité de recherche permet aux utilisateurs de rechercher à l’aide des éléments suivants :
  
- **Recherchez par nom d’affichage, par exemple « John Doe »** : cela peut renvoyer de nombreux résultats. Vous risquez donc de ne pas trouver ce que vous recherchez.
    
- **Recherche par nom d’affichage et emplacement, par exemple « John Doe à Barcelone »** : cela réduit considérablement les résultats de la recherche.
    
- **Recherche par e-mail, exemple « johndoe@outlook.com »** : cela doit retourner un résultat dans la plupart des cas ; qui correspond exactement à l’e-mail spécifié. Toutefois, si le même e-mail est associé à plusieurs comptes, plusieurs résultats peuvent être retournés.
    
- **Rechercher par numéro de téléphone, par exemple « 123-123-1234 »** : cela doit retourner un résultat dans la plupart des cas; celui qui correspond exactement au téléphone spécifié. Téléphone nombre doit inclure le code du pays (c’est-à-dire 1-xxx-yyy-zzzz). Si le même numéro de téléphone est associé à plusieurs comptes, plusieurs résultats peuvent être retournés.
    
- **Rechercher par Skype Nom, exemple « JohnDoe1456 »** : si la correspondance exacte est trouvée, elle est retournée comme premier résultat. D’autres correspondances « name » possibles peuvent être retournées.
    
    > [!NOTE]
    > Skype recherche d’annuaire doit être en mesure de communiquer avec les adresses IP suivantes sur le port 443 : 104.40.75.246, 23.101.135.34 et 40.113.86.19. 
  
## <a name="supported-deployment-matrix-for-skype-directory-search"></a>Matrice de déploiement prise en charge pour la recherche d’annuaires Skype

Le tableau suivant décrit la prise en charge de Skype recherche d’annuaires.
  

|&nbsp;|front-end Skype Entreprise Server|Serveur Lync 2013 (ou version antérieure) Frontale|Commentaires|
|:-----|:-----|:-----|:-----|
|Skype Entreprise Server Edge   |Pris en charge   |Non pris en charge   |Skype Entreprise Server et Edge sont des prérequis pour la recherche d’annuaires Skype   |
|Skype Entreprise Server Edge + Lync Server 2013 Edge déployé côte à côte   |Pris en charge   |Non pris en charge   |Skype trafic de recherche d’annuaire transite par Skype Entreprise Server serveurs Edge. Le trafic de fédération passe par la périphérie configurée par l’administrateur. Par exemple, l’administrateur peut choisir de continuer à envoyer le trafic de fédération via des serveurs Edge Lync Server 2013 qui ne prennent pas en charge Skype recherche d’annuaires.   |
|Lync Server 2013 (ou version antérieure) Edge   |Non pris en charge   |Non pris en charge   ||
   
> [!NOTE]
> Le service de carnet d’adresses s’exécutant sur Skype Entreprise Server front-end trouve edge par l’existence du port de recherche Skype 4443 dans le serveur Edge. 
  
> [!NOTE]
> Si un client a plusieurs sites dans son déploiement local, et s’il n’a déployé qu’un seul serveur/pool edge Skype Entreprise Server, le trafic de recherche provenant de tous les sites passe par le serveur Edge unique disponible. L’administrateur doit s’assurer que les pools de tous les sites peuvent accéder au serveur/pool Edge Skype Entreprise Server déployé. 
  
> [!NOTE]
> Skype service graphe limite les demandes de recherche provenant de n’importe quel client local ou Microsoft 365 ou Office 365 si le taux de demande dépasse 15 demandes par seconde. 
  
> [!NOTE]
> Pour les clients locaux de grande entreprise, les domaines doivent être ajoutés à une liste verte avec le service de recherche Skype afin d’autoriser des taux de demande plus élevés.
  
> [!NOTE]
> Skype Entreprise Server limitera les demandes entrantes, s’il y a trop de requêtes en attente dans la file d’attente. 
  
## <a name="deploying-skype-connectivity-for-skype-for-business-online"></a>Déploiement de la connectivité Skype pour Skype Entreprise Online

Skype Connectivity est également une fonctionnalité de Skype Entreprise Online, qui fait partie de Microsoft 365 et de Office 365. Vous pouvez activer la fonctionnalité de connectivité Skype à partir du Centre d’administration Skype Entreprise dans le Centre d'administration Microsoft 365.
  
Pour Microsoft 365 Midsize Business, Office 365 Entreprise, Microsoft 365 Éducation et Office 365 for Government : connectez-vous au Centre d'administration Microsoft 365 et accédez à centre d’administration Skype Entreprise. Accédez à Communications externes. Sous Fournisseurs de services de messagerie instantanée publics, cliquez sur Activer. Si vous souhaitez contrôler l’accès des utilisateurs individuels à Skype Connectivité, vous pouvez le faire en modifiant les paramètres de communication externe des utilisateurs individuels.
  
Pour Office 365 Petite Entreprise Premium : connectez-vous à Office 365 et accédez à Administration \> Service Paramètres \> messagerie instantanée, réunions et conférences. Activez les communications externes. Le commutateur de communications externes active la connectivité Skype et les communications avec d’autres organisations qui utilisent Skype Entreprise.
  
Pour plus d’informations sur l’administration Skype Entreprise Online, consultez :
  
- [Autoriser les utilisateurs à contacter des utilisateurs Skype Entreprise externes](../../SfbOnline/set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)

- [Que faire si vous ne pouvez pas Skype Entreprise de messagerie instantanée ou Skype contacts externes](https://support.office.com/article/What-to-try-if-you-cant-IM-Skype-for-Business-Lync-or-Skype-external-contacts-87f6d5d7-3b8c-4196-9c8c-1dabb75f54b8?ui=en-US&amp;rs=en-US&amp;ad=US)
    
- [Ajouter un contact dans Skype Entreprise](https://support.office.com/article/Add-a-contact-in-Skype-for-Business-89338023-2adf-4f5c-90b6-f8b6f72fadd1)
  
- [Administrateurs : configurer Skype Entreprise paramètres pour les utilisateurs individuels](../../SfbOnline/set-up-skype-for-business-online/configure-skype-for-business-settings-for-individual-users.md)
    
## <a name="deploying-skype-connectivity-for-skype-for-business-server"></a>Déploiement de la connectivité Skype pour Skype Entreprise Server

Skype Entreprise Server utilise l’architecture d’accès de fédération pour prendre en charge la connectivité avec Skype. Cette connectivité permet à vos utilisateurs Skype Entreprise Server d’ajouter des Skype. Skype clients peuvent également ajouter Skype Entreprise utilisateurs à leur liste de contacts. En fonction des stratégies définies administrativement dans Skype Entreprise Server les utilisateurs pourront communiquer à l’aide de la messagerie instantanée, voir la présence de l’autre et lancer des appels audio et vidéo. Skype connectivité est également une fonctionnalité de Skype Entreprise Online et peut être activée pour les clients Skype Entreprise Online à partir du centre d’administration Skype Entreprise dans le Centre d'administration Microsoft 365.
  
> [!NOTE]
> Si Skype Entreprise Server est déjà configuré pour se connecter à Windows Messenger à l’aide du pic (Public Instant Messaging Connectivity), votre déploiement est déjà configuré pour Skype connectivité. La seule modification que vous pouvez envisager consiste à renommer votre entrée PIC Messenger existante en tant que Skype. 
  
### <a name="the-skype-for-business-server-public-im-connectivity-provisioning-site-is-no-longer-available"></a>Le Skype Entreprise Server site d’approvisionnement de connectivité de messagerie instantanée publique n’est plus disponible

Le site qui était auparavant utilisé pour approvisionner manuellement la fédération entre Skype Entreprise déploiements locaux et Skype n’est plus nécessaire et sera arrêté le 15/08/2019. La fédération avec Skype utilise désormais la découverte de partenaires fédérés, qui est le même mécanisme requis pour la fédération avec Skype Entreprise Online.

La communication entre tout déploiement Skype Entreprise local et les utilisateurs Skype via l’infrastructure de messagerie instantanée publique existante nécessite désormais que la configuration du serveur Edge local soit compatible avec Skype Entreprise Online.

> [!NOTE]
> Aucune action n’est nécessaire pour la plupart des clients, y compris tous les déploiements fédérés avec Skype Entreprise Online.
  
Les déploiements locaux sont nécessaires pour publier un enregistrement SRV DNS de fédération pour chaque domaine qu’ils hébergent. Des conseils sont disponibles dans la [planification DNS](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#dns-planning). Chaque domaine doit être résolu par une requête SRV DNS en un nom de domaine complet de serveur edge qui satisfait à une correspondance de suffixe de niveau supérieur du domaine. Par exemple, considérez le domaine « contoso.com » :

|**Noms de domaine complets valides**|**Commentaire**|
|:-----|:-----|
|sip.contoso.com   ||
|sipfed.contoso.com   |Dans chaque cas, le nom de domaine complet exact doit être présent dans le SN ou le SAN du certificat externe installé sur le serveur de périphérie.   |
|access.contoso.com   ||
|**Noms de domaine complets non valides**|**Raison**|
|sip.contoso-edge.com   |Il ne s’agit pas d’une correspondance de suffixe.  |
|sip.it.contoso.com   |Il ne s’agit pas d’une correspondance de suffixe de niveau supérieur.   |

Vous trouverez des conseils supplémentaires sur les certificats externes dans la [planification des certificats](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#certificate-planning).

#### <a name="faqs"></a>FAQ

**Pourquoi le site web d’approvisionnement est-il arrêté ?**
Le mécanisme d’approvisionnement de messagerie instantanée (PIC) public (pic.lync.com) déployé en 2006 n’est plus utilisable et sera arrêté le 15/08/2019. Au lieu de cela, la fédération de messagerie instantanée publique suppose le même modèle de fédération utilisé par Skype Entreprise Online, connu sous le nom de « découverte de partenaire », par lequel un déploiement local est publiquement détectable par ses enregistrements SRV DNS de fédération.

**Ce changement signifie-t-il que la fédération de messagerie instantanée publique est déconseillée ?**
Non. La fédération de messagerie instantanée publique continuera d’être prise en charge pendant de nombreuses années, probablement jusqu’à ce que le Skype Entreprise produit local atteigne la fin de vie.

**Notre entreprise a une relation hybride (espace d’adressage partagé) avec Skype Entreprise Online, sommes-nous affectés ?**
Non, étant donné que vous fédérer avec Skype Entreprise Online, cette modification ne vous affectera pas.
 
**Ce changement signifie-t-il que notre entreprise doit activer la fédération avec Skype Entreprise Online ?**
Non. Si vos paramètres de proxy de serveur edge n’activent pas la fédération avec le fournisseur d’hébergement Skype Entreprise Online (sipfed.online.lync.com), cette modification n’affecte pas cela. Toutefois, les mêmes exigences de DNS et de certificat qui s’appliquent à la fédération avec Skype Entreprise Online s’appliquent désormais également à la fédération avec Skype utilisateurs.
 
**Notre entreprise est grande et ne peut pas modifier sa configuration de périphérie pour des raisons réglementaires/conformité/etc ... que pouvons-nous faire?**
Toute organisation locale qui ne peut pas modifier sa configuration de serveur de périphérie comme spécifié doit contacter la prise en charge du produit dès que possible.

### <a name="enabling-federation-and-public-im-connectivity-pic"></a>Activation de la fédération et de la connectivité de messagerie instantanée publique (PIC)

À présent, concentrez-vous sur les tâches d’environnement Skype Entreprise Server et d’administration requises pour configurer Skype connectivité. Dans cette section, nous partons du principe que l’administrateur a déployé Skype Entreprise Server et configuré l’accès externe, également appelés serveurs Edge. 
  
Trois étapes principales sont requises pour activer la fédération et le pic. Il s’agit des éléments suivants :
  
1. Configurer la fédération et le pic
    
2. Configurer au moins une stratégie pour prendre en charge l’accès des utilisateurs fédérés
    
3. Configurer le paramètre de fournisseur pic Skype
    
#### <a name="1-configure-federation-and-pic"></a>1. Configurer la fédération et le pic

La fédération est nécessaire pour permettre aux utilisateurs Skype de communiquer avec Skype Entreprise utilisateurs de votre organisation. La connectivité de messagerie instantanée publique (PIC) est une classe de fédération, et elle doit être configurée pour permettre à vos utilisateurs Skype Entreprise de communiquer avec Skype utilisateurs. La fédération et le pic sont configurés à l’aide de la Skype Entreprise Server Panneau de configuration.
  
> [!NOTE]
> La fédération PIC n’est plus prise en charge par les versions de produit antérieures à Lync Server 2010 (Live Communication Server, Office Communications Server). Les plateformes prises en charge pour la fédération PIC incluent Skype Entreprise Server, Lync Server 2013 et Lync Server 2010. 
  
La fédération est nécessaire pour permettre aux utilisateurs Skype de communiquer avec Skype Entreprise utilisateurs de votre organisation. La connectivité de messagerie instantanée publique (PIC) est une classe de fédération, et elle doit être configurée pour permettre à vos utilisateurs Skype Entreprise Server de communiquer avec Skype utilisateurs. La fédération et le pic sont configurés à l’aide de la boîte de dialogue de configuration Edge du Skype Entreprise Server Panneau de configuration, comme illustré dans la figure.
  
![Définissez un nouveau pool Edge.](../media/32d7f255-c6ad-426d-96c2-2ef4d81f3b51.png)
  
> [!NOTE]
> Les attributs EnableSkypeIdRouting et EnableSkypeDirectorySearch doivent être définis sur true dans les paramètres du fournisseur public (voir les instructions ultérieures) pour que la recherche fonctionne. 
  
Cela permet d’effectuer les tâches administratives qui doivent être effectuées sur le serveur. Vous êtes maintenant configuré pour Skype connectivité.
  
#### <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2. Configurer au moins une stratégie pour prendre en charge l’accès des utilisateurs fédérés

À l’aide de la Skype Entreprise Server Panneau de configuration, un administrateur doit configurer une ou plusieurs stratégies d’accès utilisateur externe pour contrôler si Skype utilisateurs peuvent collaborer avec des utilisateurs Skype Entreprise Server internes.
  
#### <a name="3-configure-the-skype-pic-provider-setting"></a>3. Configurer le paramètre de fournisseur pic Skype

À l’aide de Skype Entreprise Server Management Shell, un administrateur doit configurer la stratégie client Skype Entreprise pour afficher Skype en tant que fournisseur PIC supplémentaire. 
  
> [!NOTE]
> Les utilisateurs des fournisseurs de services pic (Public Instant Messaging Connectivity) ne peuvent pas participer à la messagerie instantanée ou aux conférences de votre organisation tant que vous n’avez pas configuré au moins une stratégie (étape 2, plus haut dans cette procédure) pour prendre en charge la connectivité de messagerie instantanée publique. 
  
Pour les nouvelles installations, vous pouvez configurer Skype connectivité en activant un fournisseur public Skype à l’aide de la Skype Entreprise Server Panneau de configuration, comme illustré dans la figure.
  
![Fournisseurs fédérés SIP.](../media/8fc7b566-72b5-4c43-961c-9249fdf7e575.png)
  
> [!NOTE]
> Pour configurer Skype Connectivité lors de la mise à niveau vers Skype Entreprise Server vous devez supprimer et rajouter le fournisseur public Skype existant. 
  
La configuration de la connectivité Skype peut également être effectuée à l’aide de PowerShell uniquement. Pour configurer Skype connectivité à l’aide de PowerShell :
  
1. À partir d’un serveur frontal Skype Entreprise Server, ouvrez l’interpréteur de commandes de gestion Skype Entreprise Server.
    
2. Exécutez les deux commandes suivantes :
    
   ```powershell
    Remove-CsPublicProvider -Identity <identity-name>
   ```

    > [!NOTE]
    > Si vous n’avez pas encore de fournisseur PIC dans votre environnement et que vous créez un fournisseur PIC, vous n’avez pas besoin d’exécuter l’applet de commande Remove-CsPublicProvider. 
  
   ```powershell
   New-CsPublicProvider -Identity Skype -ProxyFqdn federation.messenger.msn.com -IconUrl https://images.edge.messenger.live.com/Messenger_16x16.png -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -Enabled $true -EnableSkypeIdRouting $true -EnableSkypeDirectorySearch $true
   ```

    Que font les paramètres moins évidents ?
    
   - ProxyFqdn : emplacement de Skype edge de fédération (détenu/géré par Microsoft)
    
   - IconURL : icône utilisée par le client Skype Entreprise Lync &amp; pour identifier visuellement Skype contacts
    
   - NameDecorationRoutingDomain et NameDecorationExcludedDomainList : la définition de ces paramètres permet aux utilisateurs d’entrer Skype MSA des utilisateurs sans avoir à connaître les domaines non Microsoft « décorés » avec « msn.com ». Cela évite d’avoir à taper « user(contoso.com)@msn.com » pour tous les domaines qui ne figurent PAS dans ExcludedDomainList. Le client SfB met automatiquement en forme la MSA si le domaine ne figure PAS dans la liste Exclus. Nous avons ajouté les domaines de compte Microsoft les plus courants à la liste exclue.
    
     > [!NOTE]
     > Le fournisseur public doit être supprimé et ajouté si des modifications sont apportées. Aucune modification sur place n’est autorisée. 
  
     > [!NOTE]
     > Ajoutés dans le client de bureau Lync Server 2013 CU5 &amp; Lync dans Office 2013 SP1, nameDecorationRoutingDomain et NameDecorationExcludedDomainList améliorent la situation où les utilisateurs Lync ajoutant Skype contacts nécessaires pour « décorer » les domaines non-Microsoft afin de les identifier et de les acheminer vers Skype (au format : user(contoso.com)@msn.com). Ces nouveaux paramètres permettent la mise en forme automatique de l’entrée de l’utilisateur d’adresse dans la boîte de dialogue « Ajouter Skype contact » avec nameDecorationRoutingDomain (qui doit être défini sur msn.com) s’il ne contient pas les domaines dans NameDecorationExcludedDomainList (nous pouvons actuellement prendre en charge msn.com, live.com, Hotmail.com, outlook.com). 
  
3. À partir d’une Skype Entreprise les utilisateurs clients peuvent désormais rechercher et ajouter un utilisateur Skype.
    
## <a name="clients-and-interoperability-matrix"></a>Clients et matrice d’interopérabilité

Le tableau suivant décrit l’état de l’interopérabilité entre la dernière version de Skype consommateur et la dernière version de Skype Entreprise.
  

|clients Skype|Ajouter des contacts, la messagerie instantanée, la présence, l’audio et l’appel vidéo|Commentaire|
|:-----|:-----|:-----|
|Skype Windows Desktop   |7.6 ou version ultérieure, Windows XP et versions ultérieures   |**NOUVEAU** : Prise en charge ajoutée pour Windows Skype client s’exécutant sur Windows XP et Windows Vista **(nécessite la dernière version du client 7.26 ou ultérieure)**  |
|Skype Mobile - Android Téléphone et tablette   |6.19 ou version ultérieure, exécution Android version 4.0.3 ou ultérieure du système d’exploitation   |Les appareils à faible spécification ne prennent peut-être pas en charge l’appel vidéo   |
|Skype Mobile - iOS   |6.11 ou version ultérieure, sur IOS 7 ou version ultérieure   |Non pris en charge sont iPhone 4 et versions antérieures, iPod 4e génération et antérieure, iPad 1ère génération   |
|mac Skype   |7,19 ou supérieur, sur Mac OS X 10,9 (Non conformistes) ou une version ultérieure   |Nécessite Mac OSX 10.9 ou version ultérieure   |
|Skype application de Windows universelle (Windows 10) Bureau et mobile   |Windows 10 (mise à jour redstone 1 ou ultérieure)   |Windows application universelle recevra la mise à jour à l’automne 2016 en ajoutant la prise en charge de l’interopérabilité   |
   
Le tableau suivant décrit l’état de l’interopérabilité entre la dernière version de Skype Entreprise et la dernière version de Skype consommateur. 
  
|Client|Skype la recherche d’annuaires et l’ajout de contacts|Skype A/V, interopérabilité par messagerie instantanée|
|:-----|:-----|:-----|
|Skype Entreprise   |Oui   |Oui   |
|Skype Entreprise sur Mac   |Peut ajouter (aucune recherche)   |Oui   |
|Lync Desktop 2013   |Peut ajouter (aucune recherche)   |Oui   |
|Application web Lync - en ligne et localement   |N/A   |S/O   |
|Lync Mobile - Windows Phone   |Bientôt disponible   |Oui   |
|Lync Mobile - Android   |Bientôt disponible   |Oui   |
|Lync Mobile - iOS   |Bientôt disponible   |Oui   |
|Lync Room System   |Bientôt disponible   |Oui   |
|Lync Modern App (Win 8.1)   |Oui   |Oui   |
|Lync Mac 2011   |Peut ajouter (aucune recherche)   |Oui   |
|Lync Desktop 2010   |Peut ajouter (aucune recherche)   |Oui   |
|Lync Phone Edition   |N/A   |S/O   |
|Lync Attendant   |N/A   |S/O   |
   
