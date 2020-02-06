---
title: Déploiement de la connectivité Skype dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fb51860b-6f46-4b71-b8c8-682d0982d36d
description: 'Résumé : Découvrez comment connecter Skype entreprise Server à Skype grand public. Également connu sous le nom de connectivité Skype.'
ms.openlocfilehash: e9c8a83b24ddbed95f2fd16f2f11b887f2241625
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798101"
---
# <a name="deploy-skype-connectivity-in-skype-for-business-server"></a>Déploiement de la connectivité Skype dans Skype entreprise Server

**Résumé :** Découvrez comment vous connecter à Skype entreprise Server avec le grand public Skype. Également connu sous le nom de connectivité Skype.
  
Cet article décrit le déploiement de la connectivité Skype.
  
## <a name="skype-connectivity-overview-for-it-professionals"></a>Vue d’ensemble de la connectivité Skype pour les professionnels de l’informatique

Skype Connectivity offre aux utilisateurs Skype entreprise la possibilité de rechercher et d’ajouter des utilisateurs Skype. Skype Connectivity est une fonction de Skype entreprise qui vous permet d’activer la Fédération et l’annuaire auprès des utilisateurs Skype. Après avoir activé la connectivité Skype, vos utilisateurs Skype entreprise pourront rechercher et ajouter des utilisateurs Skype.
  
## <a name="skype-directory-search"></a>Recherche dans l’annuaire Skype

La fonctionnalité Recherche dans l’annuaire Skype permet aux utilisateurs de Skype Entreprise de rechercher des contacts Skype. La fonctionnalité de recherche permet aux utilisateurs de rechercher des utilisateurs comme suit :
  
- **Recherche par nom d’affichage, exemple « Jean Dupont »** -cela peut retourner de nombreux résultats, afin que vous ne trouviez pas ce que vous recherchez.
    
- **Rechercher par nom d’affichage plus emplacement, exemple « John Doe à Barcelone »** -cela a pour effet de limiter considérablement les résultats de la recherche.
    
- La **recherche par courrier électronique, par exemple « JohnDoe@outlook.com »,** renvoie un résultat dans la plupart des cas. celui qui correspond exactement à l’adresse électronique spécifiée. Mais si le même e-mail est associé à plusieurs comptes, plusieurs résultats peuvent être retournés.
    
- **Recherche par numéro de téléphone, exemple « 123-123-1234 »** -cela devrait renvoyer un résultat dans la plupart des cas ; celle qui correspond exactement au téléphone spécifié. Le numéro de téléphone doit inclure le code du pays (à savoir, 1-xxx-yyy-zzzz). Si le même numéro de téléphone est associé à plusieurs comptes, plusieurs résultats peuvent être retournés.
    
- La **recherche par pseudo Skype, par exemple « JohnDoe1456 »** , si la correspondance exacte est trouvée, il sera renvoyé comme premier résultat. D’autres correspondances possibles peuvent être renvoyées.
    
    > [!NOTE]
    > La recherche dans l’annuaire Skype doit pouvoir communiquer avec les adresses IP suivantes sur le port 443 : 104.40.75.246, 23.101.135.34 et 40.113.86.19. 
  
## <a name="supported-deployment-matrix-for-skype-directory-search"></a>Matrice de déploiement prise en charge pour la Recherche dans l’annuaire Skype

Le tableau suivant présente la prise en charge pour la Recherche dans l’annuaire Skype.
  

||**Serveur frontal Skype entreprise Server**|**Serveur frontal Lync Server 2013 (ou antérieur)**|**Commentaires**|
|:-----|:-----|:-----|:-----|
|Skype entreprise Server Edge  <br/> |Pris en charge  <br/> |Non pris en charge  <br/> |Le logiciel Skype entreprise Server et Microsoft Edge sont requis pour la recherche dans l’annuaire Skype  <br/> |
|Skype entreprise Server Edge + Lync Server 2013 Edge déployé côte à côte  <br/> |Pris en charge  <br/> |Non pris en charge  <br/> |Le flux de la recherche dans l’annuaire Skype transite par les serveurs de Skype Entreprise Server Edge. Le flux de fédération passe à travers le serveur Edge configuré par l’administrateur. Par exemple, l’administrateur peut choisir de continuer à envoyer le trafic de fédération via les serveurs Edge Lync Server 2013 qui ne prennent pas en charge la recherche dans l’annuaire Skype.  <br/> |
|Serveur Edge Lync Server 2013 (ou antérieur)  <br/> |Non pris en charge  <br/> |Non pris en charge  <br/> ||
   
> [!NOTE]
> Le service AddressBook en cours d’exécution sur Skype entreprise Server front end trouve le bord par l’existence du port 4443 de recherche Skype sur le serveur Edge. 
  
> [!NOTE]
> Dans le cas où un client dispose de plusieurs sites dans leur déploiement local, et s’il a déployé un seul serveur ou pool Skype entreprise Server Edge, la recherche de trafic à partir de tous les sites passe par le biais du serveur Edge disponible unique. L’administrateur doit veiller à ce que les pools de tous les sites puissent accéder au serveur Edge et au pool Skype entreprise Server. 
  
> [!NOTE]
> Le service graphique de Skype limite les demandes de recherche émanant de tout site local ou client Office 365 si le taux de demandes dépasse 15 demandes par seconde. 
  
> [!NOTE]
> Pour les clients sur sites locaux des grandes entreprises, les domaines doivent être placés sur liste blanche auprès du service de recherche Skype pour permettre des taux de demandes plus élevés. 
  
> [!NOTE]
> Skype entreprise Server va limiter les demandes entrantes, s’il y a trop de demandes en attente dans la file d’attente. 
  
## <a name="deploying-skype-connectivity-for-skype-for-business-online-in-office-365"></a>Déploiement de la connectivité Skype pour Skype Entreprise Online dans Office 365

La connectivité Skype est également une fonctionnalité de Skype Entreprise Online, qui fait partie d’Office 365. Vous pouvez activer la fonctionnalité de connectivité Skype à partir du centre d’administration Skype Entreprise dans le portail Office 365.
  
Pour Office 365 Moyenne Entreprise, Office 365 Entreprise, Office 365 Éducation et Office 365 pour le Secteur public : connectez-vous au portail Office 365 et accédez au centre d’administration Skype Entreprise. Accédez à Communications externes. Sous Fournisseurs de service de messagerie instantanée publique, cliquez sur Activer. Pour contrôler l’accès utilisateur individuel à la connectivité Skype, vous pouvez le faire en modifiant les paramètres de communication externe des utilisateurs individuels.
  
Pour Office 365 petite entreprise Premium : Connectez-vous à Office 365, puis accédez à \> paramètres \> du service d’administration messagerie instantanée, réunions et conférences. Activez les communications externes. Le commutateur Communications externes active la connectivité Skype et les communications avec les autres organisations qui utilisent Skype Entreprise.
  
Pour plus d’informations sur l’administration de Skype Entreprise Online, voir :
  
- [Autoriser les utilisateurs à contacter des utilisateurs Skype Entreprise externes](../../SfbOnline/set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)

- [Que faire si vous ne pouvez pas utiliser la messagerie instantanée avec Skype entreprise ou les contacts externes Skype](https://support.office.com/en-us/article/What-to-try-if-you-cant-IM-Skype-for-Business-Lync-or-Skype-external-contacts-87f6d5d7-3b8c-4196-9c8c-1dabb75f54b8?ui=en-US&amp;rs=en-US&amp;ad=US)
    
- [Ajouter un contact dans Skype entreprise](https://support.office.com/en-US/article/Add-a-contact-in-Skype-for-Business-89338023-2adf-4f5c-90b6-f8b6f72fadd1)
  
- [Administrateurs : Configuration des paramètres de Skype Entreprise pour les utilisateurs individuels](../../SfbOnline/set-up-skype-for-business-online/configure-skype-for-business-settings-for-individual-users.md)
    
## <a name="deploying-skype-connectivity-for-skype-for-business-server"></a>Déploiement de la connectivité Skype pour Skype entreprise Server

Skype entreprise Server utilise l’architecture d’accès à la Fédération pour prendre en charge la connectivité avec Skype. Cette connectivité permet aux utilisateurs de Skype Entreprise Server d’ajouter Skype. Les clients de Skype peuvent également ajouter des utilisateurs Skype Entreprise dans leurs listes de contacts. En fonction des stratégies qui sont définies par les utilisateurs de Skype entreprise Server, les utilisateurs pourront communiquer à l’aide de la messagerie instantanée, voir la présence de chacun d’eux et lancer des appels audio et vidéo. La connectivité Skype est également une fonctionnalité de Skype Entreprise Online, et peut être activée pour Skype Entreprise Online à partir du centre d’administration Skype Entreprise dans le portail Office 365.
  
> [!NOTE]
> Si Skype Entreprise Server est configuré pour se connecter à Windows Messenger via la connectivité PIC (Public IM Connectivity), votre déploiement est déjà configuré pour la connectivité Skype. Vous pouvez éventuellement renommer votre entrée Messenger PIC existante pour utiliser Skype.  
  
### <a name="the-skype-for-business-server-public-im-connectivity-provisioning-site-is-no-longer-available"></a>Le site de mise en service de la connectivité de messagerie instantanée publique de Skype entreprise Server n’est plus disponible

Le site précédemment utilisé pour approvisionner manuellement la Fédération entre les déploiements locaux de Skype entreprise et Skype n’est plus nécessaire et sera arrêté dans 8/15/2019. La Fédération avec Skype utilise désormais la découverte de partenaire fédéré, qui est le même mécanisme requis pour la Fédération avec Skype entreprise online.

La communication entre le déploiement de Skype entreprise local et les utilisateurs Skype par le biais de l’infrastructure de messagerie instantanée publique existante nécessite désormais la compatibilité de la configuration du serveur Edge sur site avec Skype entreprise online.

> [!NOTE]
> Aucune action n’est nécessaire pour la plupart des clients, y compris tous les déploiements qui se fédérer dans Skype entreprise online.
  
Les déploiements sur site sont requis pour publier un enregistrement SRV DNS de Fédération pour chaque domaine qu’il héberge. Les recommandations sont disponibles dans la [planification DNS](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#dns-planning). Chaque domaine doit résoudre par la requête DNS SRV en un nom de domaine complet (FQDN) de serveur Edge qui répond à une correspondance de suffixe de niveau supérieur du domaine. Par exemple, considérez le domaine « contoso.com » :

|**Noms de domaine complets valides**|**Commentaire**|
|:-----|:-----|
|sip.contoso.com   ||
|sipfed.contoso.com   |Dans chaque cas, le nom de domaine complet exact doit être présent dans le réseau SN ou le SAN du certificat externe installé sur le serveur Edge.   |
|access.contoso.com   ||
|**Noms de domaine complets non valides**|**Raison**|
|sip.contoso-edge.com   |Ce ne correspond pas à un suffixe.  |
|sip.it.contoso.com   |Il n’existe pas de suffixe de niveau supérieur.   |

Pour plus d’informations sur les certificats externes, reportez-vous à la rubrique [planification de certificat](../plan-your-deployment/edge-server-deployments/edge-environmental-requirements.md#certificate-planning).

#### <a name="faqs"></a>Questions

**Pourquoi le site Web de mise en service est-il arrêté ?**
Le mécanisme de mise en service de messagerie instantanée (im) public qui a été déployé dans 2006 ne peut plus être utilisé et sera arrêté sur 8/15/2019. Au lieu de cela, la Fédération publique doit supposer le même modèle de Fédération utilisé par Skype entreprise Online, connu sous le nom de « découverte de partenaire », qui permet de détecter publiquement un déploiement local par son ou ses enregistrements SRV DNS de Fédération.

**Cette modification signifie-t-elle que la Fédération de messagerie instantanée publique est déconseillée ?**
Non. La Fédération de messagerie instantanée publique restera prise en charge pendant plusieurs années, sans doute que le produit local Skype entreprise n’atteint la fin de vie.

**Notre entreprise est dotée d’une relation hybride (espace d’adresse partagée) avec Skype entreprise online.**
Non, puisque vous vous êtes déjà connecté à Skype entreprise Online, cette modification n’aura aucun effet.
 
**Ce changement signifie-t-il que notre entreprise doit activer la Fédération avec Skype entreprise Online ?**
Non. Si les paramètres de proxy de votre serveur Edge n’autorisent pas la Fédération avec le fournisseur d’hébergement Skype entreprise Online (sipfed.online.lync.com), cette modification n’a pas d’incidence sur celle-ci. Toutefois, les mêmes exigences DNS et de certificats qui s’appliquent à la Fédération avec Skype entreprise Online s’appliquent également à la Fédération avec les utilisateurs de Skype.
 
**Notre entreprise est volumineuse et ne peut pas modifier sa configuration latérale en raison de la réglementation et de la conformité, etc. que faire ?**
Toutes les organisations locales qui ne peuvent pas modifier la configuration de votre serveur de périmètre comme indiqué doivent communiquer au support technique le plus tôt possible.

### <a name="enabling-federation-and-public-im-connectivity-pic"></a>Activation de la fédération et de la connectivité PIC (Public IM Connectivity)

Concentrez-vous désormais sur l’environnement Skype entreprise Server et les tâches d’administration nécessaires à la configuration de la connectivité Skype. Cette section suppose que l’administrateur a déployé Skype Entreprise Server et configuré l’accès externe, appelé serveurs Edge. 
  
Trois étapes sont nécessaires pour activer la fédération et PIC :
  
1. Configurer la fédération et PIC
    
2. Configurer au moins une stratégie pour la prise en charge de l’accès des utilisateurs fédérés
    
3. Configurer le paramètre de fournisseur PIC Skype
    
#### <a name="1-configure-federation-and-pic"></a>1. Configurer la fédération et la connectivité PIC

La fédération est requise pour permettre aux utilisateurs Skype de communiquer avec les utilisateurs Skype Entreprise dans votre organisation. La connectivité PIC (Public IM Connectivity) est une classe de fédération. Elle doit être configurée pour permettre à vos utilisateurs Skype Entreprise de communiquer avec les utilisateurs Skype. La fédération et la connectivité PIC sont configurées à l’aide du panneau de configuration Skype Entreprise Server.
  
> [!NOTE]
> La Fédération PIC n’est plus prise en charge par les versions de produits antérieures à Lync Server 2010 (Live Communication Server, Office Communications Server). Les plateformes prises en charge pour la Fédération PIC incluent Skype entreprise Server, Lync Server 2013 et Lync Server 2010. 
  
La fédération est requise pour permettre aux utilisateurs Skype de communiquer avec les utilisateurs Skype Entreprise dans votre organisation. La connectivité PIC (Public IM Connectivity) est une classe de fédération. Elle doit être configurée pour permettre à vos utilisateurs Skype Entreprise de communiquer avec les utilisateurs Skype. La fédération et la connectivité PIC sont configurées à l’aide de la boîte de dialogue Configuration du serveur Edge du panneau de configuration Skype Entreprise Server, comme le montre la figure.
  
![Définir le nouveau pool Edge](../media/32d7f255-c6ad-426d-96c2-2ef4d81f3b51.png)
  
> [!NOTE]
> Les attributs EnableSkypeIdRouting et EnableSkypeDirectorySearch doivent être définis sur True dans les paramètres du fournisseur public (voir les instructions plus loin) pour que la recherche fonctionne. 
  
Cette procédure termine les tâches d’administration qui doivent être effectuées sur le serveur. Vous pouvez à présent utiliser la connectivité Skype.
  
#### <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2. configurer au moins une stratégie pour prendre en charge l’accès des utilisateurs fédérés

À l’aide du panneau de configuration Skype Entreprise Server, l’administrateur doit configurer une ou plusieurs stratégies d’accès des utilisateurs externes pour contrôler la possibilité pour les utilisateurs Skype de collaborer avec les utilisateurs Skype Entreprise Server internes.
  
#### <a name="3-configure-the-skype-pic-provider-setting"></a>3. Configurez le paramètre du fournisseur de PIC Skype

À l’aide de Skype Entreprise Server Management Shell, l’administrateur doit configurer la stratégie de client Skype Entreprise pour afficher Skype comme fournisseur PIC supplémentaire.  
  
> [!NOTE]
> Les utilisateurs des fournisseurs de service de messagerie instantanée publique ne peuvent pas participer à la messagerie instantanée ou aux conférences dans votre organisation tant que vous n’avez pas configuré au moins une stratégie (étape 2, plus haut dans cette procédure) pour la prise en charge de la connectivité de messagerie instantanée publique. 
  
Pour les nouvelles installations, vous pouvez configurer la connectivité Skype en activant un fournisseur public Skype à l’aide du panneau de configuration Skype Entreprise Server, comme illustré.
  
![Fournisseurs fédérés SIP](../media/8fc7b566-72b5-4c43-961c-9249fdf7e575.png)
  
> [!NOTE]
> Pour configurer la connectivité Skype lors de la mise à niveau vers Skype Entreprise Server, vous devez supprimer puis rajouter le fournisseur public Skype existant. 
  
Vous pouvez également configurer la connectivité Skype à l’aide uniquement de PowerShell. Pour configurer la connectivité Skype à l’aide de PowerShell :
  
1. À partir d’un serveur frontal Skype Entreprise Server, ouvrez Skype Entreprise Server Management Shell.
    
2. Exécutez les deux commandes suivantes :
    
   ```powershell
    Remove-CsPublicProvider -Identity <identity-name>
   ```

    > [!NOTE]
    > Si vous ne disposez pas encore d’un fournisseur PIC dans votre environnement et que vous créez un nouvel environnement PIC, vous n’avez pas besoin d’exécuter l’applet de commande Remove-CsPublicProvider.  
  
   ```powershell
   New-CsPublicProvider -Identity Skype -ProxyFqdn federation.messenger.msn.com -IconUrl https://images.edge.messenger.live.com/Messenger_16x16.png -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -Enabled $true -EnableSkypeIdRouting $true -EnableSkypeDirectorySearch $true
   ```

    À quoi servent les paramètres les moins évidents ?
    
   - ProxyFqdn : emplacement du serveur Edge de fédération Skype (détenu/géré par Microsoft)
    
   - IconURL : icône utilisée par le &amp; client Skype entreprise de Lync pour identifier visuellement les contacts Skype
    
   - NameDecorationRoutingDomain et NameDecorationExcludedDomainList : le fait de les configurer permet aux utilisateurs d’entrer sur le MSAs de Skype sans avoir besoin de se familiariser avec les domaines « décorer » et non Microsoft avec « msn.com ». Cela évite d’avoir à taper « User (contoso. com) @msn. com » pour tous les domaines qui ne figurent pas dans le ExcludedDomainList. Le client Skype Entreprise formate automatiquement le compte Microsoft si le domaine ne figure PAS dans la liste Exclus. Nous avons ajouté les domaines de compte Microsoft les plus courants à la liste exclus.
    
     > [!NOTE]
     > Il est nécessaire de supprimer le fournisseur public puis de le rajouter en cas de nouvelles modifications. Aucune modification sur place n’est admise. 
  
     > [!NOTE]
     > Ajouté dans Lync Server 2013 CU5 &amp; le client de bureau Lync dans Office 2013 SP1, le NameDecorationRoutingDomain et NameDecorationExcludedDomainList améliorer la situation dans laquelle les utilisateurs de Lync qui ajoutent des contacts Skype ont besoin de « décorer » des domaines non Microsoft pour les identifier et les acheminer vers Skype (format : utilisateur (contoso. com) @msn. com). Ces nouveaux paramètres autorisent la mise en forme automatique de l’adresse dans la boîte de dialogue « Ajouter un contact Skype » avec le NameDecorationRoutingDomain (qui doit être défini sur msn.com) s’il ne contient pas les domaines du NameDecorationExcludedDomainList ( pour l’instant, nous pouvons prendre en charge msn.com, live.com, Hotmail.com, outlook.com). 
  
3. À partir d’un client Skype Entreprise, les utilisateurs peuvent maintenant rechercher et ajouter un utilisateur Skype.
    
## <a name="clients-and-interoperability-matrix"></a>Matrice clients et interopérabilité

Le tableau ci-dessous décrit l’état d’interopérabilité entre la dernière version de Skype et la dernière version de Skype Entreprise.
  

|**Clients Skype**|**Ajouter des contacts, messagerie instantanée, présence, son et appels vidéo**|**Commentaire**|
|:-----|:-----|:-----|
|Skype Windows Desktop  <br/> |version 7.6 ou supérieure, Windows XP et version supérieure  <br/> |**Nouveauté**: prise en charge du client Windows Skype exécuté sur Windows XP et Windows Vista **(nécessite la version 7,26 ou une version ultérieure)** <br/> |
|Skype Mobile - Téléphone Android et tablette   <br/> |version 6.19 ou supérieure, sur Android OS version 4.0.3 ou supérieure  <br/> |Les périphériques dont la configuration est faible peuvent ne pas prendre en charge les appels vidéo  <br/> |
|Skype mobile-iOS  <br/> |version 6.11 ou supérieure, sur iOS 7 ou version supérieure  <br/> |iPhone 4 et versions inférieures, iPod 4ème génération et versions inférieures, iPad 1ère génération non pris en charge  <br/> |
|Skype Mac  <br/> |version 7.19 ou supérieure, sur Mac OS X 10.9 (Mavericks) ou version supérieure  <br/> |Nécessite Mac OS X 10.9 ou version supérieure  <br/> |
|Skype Universal Windows App (Windows 10), bureau et mobile  <br/> |Windows 10 (mise à jour Redstone 1 ou version supérieure)  <br/> |L’application universelle Windows fera l’objet d’une mise à jour à l’automne 2016 qui lui apportera la prise en charge de l’interopérabilité  <br/> |
   
Le tableau ci-dessous décrit l’état d’interopérabilité entre la dernière version de Skype Entreprise et la dernière version de Skype.  
  
|**Client**|**Recherche dans l’annuaire Skype et ajout de contacts**|**Skype A/V, interopérabilité avec la messagerie instantanée**|
|:-----|:-----|:-----|
|Skype Entreprise  <br/> |Oui  <br/> |Oui  <br/> |
|Skype Entreprise sur Mac  <br/> |Ajout possible (pas de recherche)  <br/> |Oui  <br/> |
|Lync Desktop 2013  <br/> |Ajout possible (pas de recherche)  <br/> |Oui  <br/> |
|Lync Web App - en ligne et sur site  <br/> |N/D  <br/> |N/D  <br/> |
|Lync Mobile - Windows Phone  <br/> |Bientôt disponible  <br/> |Oui  <br/> |
|Lync Mobile - Android  <br/> |Bientôt disponible  <br/> |Oui  <br/> |
|Lync Mobile - iOS  <br/> |Bientôt disponible  <br/> |Oui  <br/> |
|Lync Room System  <br/> |Bientôt disponible  <br/> |Oui  <br/> |
|Lync Modern App (Windows 8.1)  <br/> |Oui  <br/> |Oui  <br/> |
|Lync Mac 2011  <br/> |Ajout possible (pas de recherche)  <br/> |Oui  <br/> |
|Lync Desktop 2010  <br/> |Ajout possible (pas de recherche)  <br/> |Oui  <br/> |
|Lync Phone Edition  <br/> |N/D  <br/> |N/D  <br/> |
|Lync Attendant  <br/> |N/A  <br/> |N/A  <br/> |
   

