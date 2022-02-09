---
title: Déployer et configurer la mobilité pour Skype Entreprise Server
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
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: Cet article vous explique comment configurer une installation Skype Entreprise Server existante pour utiliser le service de mobilité, ce qui permet à vos appareils mobiles de tirer parti des fonctionnalités de mobilité Skype Entreprise Server.
ms.openlocfilehash: b6d99c18f17158ae8b999320b767b1cc07d44dd5
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62397494"
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server"></a>Déployer et configurer la mobilité pour Skype Entreprise Server  
 
Cet article vous explique comment configurer une installation Skype Entreprise Server existante pour utiliser le service de mobilité, ce qui permet à vos appareils mobiles de tirer parti des fonctionnalités de mobilité Skype Entreprise Server.
  
Après avoir consulté [l’article Plan for Mobility for Skype Entreprise Server](../plan-your-deployment/mobility.md), vous devez être prêt à suivre les étapes ci-dessous pour déployer la mobilité dans Skype Entreprise Server environnement. Les étapes sont les suivantes (et nous allons inclure dans ce tableau une liste d’autorisations) :
  
|**Étape**|**Autorisations**|
|:-----|:-----|
|[Créer des enregistrements DNS](deploy-and-configure-mobility.md#CreateDNSRec) <br/> |Administrateurs du domaine  <br/> Administrateurs DNS  <br/> |
|[Modifier les certificats](deploy-and-configure-mobility.md#ModCerts) <br/> |Administrateur local  <br/> |
|[Configurer le proxy inverse](deploy-and-configure-mobility.md#ConfigRP) <br/> |Administrateur local  <br/> |
|[Configurer la découverte automatique pour la mobilité avec des déploiements hybrides](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |Administrateurs du domaine  <br/> |
|[Tester votre déploiement de mobilité](deploy-and-configure-mobility.md#TestMobility) <br/> |CsAdministrator  <br/> |
|[Configurer les notifications de type push](deploy-and-configure-mobility.md#ConfigPush) <br/> |RtcUniversalServerAdmins  <br/> |
|[Configurer la stratégie de mobilité](deploy-and-configure-mobility.md#ConfigMob) <br/> |CsAdministrator  <br/> |
   
Toutes les sections suivantes contiennent des étapes qui supposent que vous avez lu la rubrique Planification. Si vous êtes déconcertant, n’hésitez pas à consulter les informations qu’il vous reste.

> [!NOTE]
> La prise en charge de MCX (Mobility Service) pour les clients mobiles hérités n’est plus disponible Skype Entreprise Server 2019. Tous les clients mobiles Skype Entreprise actuellement utilisent déjà l’API UCWA (Unified Communications Web API) pour prendre en charge la messagerie instantanée, la présence et les contacts. Les utilisateurs ayant des clients hérités utilisant MCX devront mettre à niveau vers un client actuel.
  
## <a name="create-dns-records"></a>Créer des enregistrements DNS
<a name="CreateDNSRec"> </a>

Vous en avez peut-être déjà dans le cadre de votre environnement Skype Entreprise Server, mais vous devez créer les enregistrements suivants pour que la découverte automatique fonctionne :
  
- Un enregistrement DNS interne pour prendre en charge les utilisateurs mobiles qui se connectent à partir du réseau de votre organisation.
    
- Un enregistrement DNS externe (ou public) pour prendre en charge les utilisateurs mobiles qui se connectent depuis l’extérieur du réseau de votre organisation.
    
Ces enregistrements peuvent être des noms A (hôte) ou des enregistrements CNAME (vous n’avez pas besoin d’effectuer les deux, nous allons simplement inclure les étapes pour tous les éléments ici).
  
### <a name="create-an-internal-dns-cname-record"></a>Créer un enregistrement CNAME DNS interne

1. Connectez-vous à un serveur DNS de votre réseau qui est membre du groupe **Administrateurs** du domaine ou du groupe **DnsAdmins** .
    
2. **Cliquez sur** Démarrer, Choisissez outils d’administration **(vous** devrez peut-être le rechercher s’il ne s’agit pas d’une option en dehors du menu Démarrer), puis cliquez sur **DNS** pour ouvrir le logiciel en ligne d’administration DNS.
    
3. Dans le volet gauche de la fenêtre de la console, vous devez aller dans le domaine qui est le domicile des serveurs frontux de votre Skype Entreprise Server et y développer les **zones** de recherche avant.
    
4. Prenez un moment pour voir lequel des deux cas suivants vous avez :
    
   - Tout enregistrement A ou AAAA d’hôte pour votre serveur frontal (standard ou Enterprise) ou pool(s) frontal(s).
    
   - Tout enregistrement A ou AAAA d’hôte pour un directeur ou un pool directeur (configuration facultative que vous pouvez avoir dans votre déploiement).
    
5. Une fois que vous avez noté cela, cliquez avec le bouton droit sur votre nom de domaine SIP, puis sélectionnez **Nouvel alias (CNAME)** dans le menu.
    
6. Dans la boîte de **texte Nom d’alias** , tapez lyncdiscoverinternal comme nom d’hôte, pour l’URL du service de découverte automatique interne.
    
7. Dans le nom de domaine complet **(FQDN** pour l’hôte cible), vous devez taper ou parcourir le nom de domaine complet des services web internes pour votre pool frontal (ou serveur frontal unique, ou pool directeur ou directeur), identifié à l’étape 4 ci-dessus. Cliquez sur OK lorsqu’il est entré.
    
8. Vous devez créer un enregistrement CNAME de découverte automatique dans la zone de recherche avant pour chaque domaine SIP pris en charge dans votre environnement Skype Entreprise Server.
    
### <a name="create-an-external-dns-cname-record"></a>Créer un enregistrement CNAME DNS externe

1. Ces étapes sont génériques, car nous ne pouvons pas savoir quel fournisseur DNS public vous utilisez, mais nous voulons quand même vous aider. Connectez-vous à votre fournisseur DNS public avec un compte qui pourra y effectuer de nouveaux enregistrements DNS.
    
2. À ce stade, un domaine SIP doit déjà exister pour Skype Entreprise Server. Développez **la zone de recherche avant** pour ce domaine SIP ou ouvrez-la.
    
3. Prenez un moment pour voir lequel des deux cas suivants vous avez :
    
   - Tout enregistrement A ou AAAA d’hôte pour votre serveur frontal (standard ou Enterprise) ou pool(s) frontal(s).
    
   - Tout enregistrement A ou AAAA d’hôte pour un directeur ou un pool directeur (configuration facultative que vous pouvez avoir dans votre déploiement).
    
4. Une fois que vous avez ces informations, vous devez être en mesure de sélectionner une option pour créer un **nouvel alias (CNAME).**
    
5. Maintenant que vous devez être en mesure d’entrer un nom **d’alias**, vous devez entrer lyncdiscover ici pour l’URL du service de découverte automatique externe.
    
6. Ensuite, il doit y avoir une zone à entrer dans un nom de domaine général pour l’hôte **cible, il** doit s’agit du nom de domaine (FQDN) de votre pool frontal (ou serveur frontal unique, ou pool directeur ou directeur), identifié à l’étape 3 ci-dessus.
    
7. Vous devrez peut-être enregistrer ici, ou si vous devez créer des enregistrements CNAME supplémentaires dans la zone de recherche avant de chaque domaine SIP de votre environnement Skype Entreprise Server, vous devez le faire, mais une fois prêt, enregistrez votre travail.
    
### <a name="create-an-internal-dns-a-record"></a>Créer un enregistrement DNS A interne

1. Connectez-vous à un serveur DNS de votre réseau qui est membre du groupe **Administrateurs** du domaine ou du groupe **DnsAdmins** .
    
2. **Cliquez sur** Démarrer, Choisissez outils d’administration **(vous** devrez peut-être le rechercher s’il ne s’agit pas d’une option en dehors du menu Démarrer), puis cliquez sur **DNS** pour ouvrir le logiciel en ligne d’administration DNS.
    
3. Dans le volet gauche de la fenêtre de la console, vous devez aller dans le domaine qui est le domicile des serveurs frontux de votre Skype Entreprise Server et y développer les **zones** de recherche avant.
    
4. Prenez un moment pour voir lequel des deux cas suivants vous avez :
    
   - Tout enregistrement A ou AAAA d’hôte pour votre serveur frontal (standard ou Enterprise) ou pool(s) frontal(s).
    
   - Tout enregistrement A ou AAAA d’hôte pour un directeur ou un pool directeur (configuration facultative que vous pouvez avoir dans votre déploiement).
    
5. Une fois que vous avez noté cela, cliquez avec le bouton droit sur votre nom de domaine SIP, puis choisissez Nouvel hôte **(A ou AAAA)** dans le menu.
    
6. Dans la **boîte de** texte Nom, tapez lyncdiscoverinternal comme nom d’hôte, pour l’URL du service de découverte automatique interne.
    
7. Dans la boîte de texte Adresse **IP** , tapez l’adresse IP des services web internes pour votre pool frontal (ou serveur frontal unique, ou pool directeur ou directeur), identifiée à l’étape 4 ci-dessus.
    
8. Lorsque cela est terminé, cliquez **sur Ajouter** un hôte, puis sur **OK**.
    
9. Vous devez créer un nouvel enregistrement A ou AAAA de découverte automatique dans la zone de recherche avant pour chaque domaine SIP pris en charge dans votre environnement Skype Entreprise Server. Pour ce faire, répétez les étapes 6 à 8 autant de fois que nécessaire.
    
10. Lorsque vous avez terminé, cliquez sur **Terminé**.
    
### <a name="create-an-external-dns-a-record"></a>Créer un enregistrement DNS A externe

1. Ces étapes sont génériques, car nous ne pouvons pas savoir quel fournisseur DNS public vous utilisez, mais nous voulons quand même vous aider. Connectez-vous à votre fournisseur DNS public avec un compte qui pourra y effectuer de nouveaux enregistrements DNS.
    
2. À ce stade, un domaine SIP doit déjà exister pour Skype Entreprise Server. Développez **la zone de recherche avant** pour ce domaine SIP ou ouvrez-la.
    
3. Prenez un moment pour voir lequel des deux cas suivants vous avez :
    
   - Tout enregistrement A ou AAAA d’hôte pour votre serveur frontal (standard ou Enterprise) ou pool(s) frontal(s).
    
   - Tout enregistrement A ou AAAA d’hôte pour un directeur ou un pool directeur (configuration facultative que vous pouvez avoir dans votre déploiement).
    
4. Une fois que vous avez ces informations, vous devez être en mesure de sélectionner une option pour créer un nouvel hôte **A ou AAAA**.
    
5. Maintenant que vous devez être en mesure d’entrer un **nom, vous** devez entrer lyncdiscover ici pour l’URL du service de découverte automatique externe.
    
6. Ensuite, il doit y avoir une zone à entrer dans une adresse IP, il doit s’agit de **l’adresse** IP de votre pool frontal (ou serveur frontal unique, ou pool directeur ou directeur), identifiée à l’étape 3 ci-dessus.
    
7. Vous devrez peut-être enregistrer ici, ou si vous devez créer des enregistrements A ou AAAA supplémentaires dans la zone de recherche avant de chaque domaine SIP de votre environnement Skype Entreprise Server, vous devez le faire, mais une fois prêt, enregistrez votre travail.
    
## <a name="modify-certificates"></a>Modifier les certificats
<a name="ModCerts"> </a>

Si vous avez des questions sur la planification des certificats, nous l’avons documenté dans notre article [Plan for Mobility for Skype Entreprise Server](../plan-your-deployment/mobility.md). Une fois que vous aurez vérifié cela, nous vous passerons en revue les questions suivantes :
  
- Ai-je besoin de nouveaux certificats ?
    
- Demande de nouveaux certificats auprès de votre autorité de certification.
    
- Mise à jour de vos certificats sur place avec les remplacements à l’aide de PowerShell.
    
- Vérification des certificats à l’aide du snapin Certificats dans la console MMC (Microsoft Management Console).
    
### <a name="do-i-need-new-certificates"></a>Ai-je besoin de nouveaux certificats ?

1. Tout d’abord, vous devrez peut-être vérifier et voir quels certificats sont en place, et s’ils ont ou non les entrées dont vous avez besoin. Pour ce faire, vous devez vous connecter à votre Skype Entreprise Server compte administrateur local. Ce compte peut également avoir des droits sur l’autorité de certification émettrice pour certaines de ces étapes.
    
2. Ouvrez Skype Entreprise Server Management Shell (vous pouvez utiliser la recherche pour la trouver si vous ne l’avez pas épinglée à votre menu Démarrer ou barre des tâches).
    
3. Il sera essentiel de savoir quels certificats ont été affectés avant d’essayer d’ajouter un certificat mis à jour. À partir de la commande, tapez :
    
   ```powershell
   Get-CsCertificate
   ```

4. Les informations de l’étape 3 vous seront propres. Vous devez l’examiner pour déterminer si vous avez un certificat unique affecté à plusieurs éléments ou si un certificat différent est affecté pour les différents composants qui en ont besoin. Le **paramètre Use** vous indique comment un certificat est utilisé et le paramètre **Thumbprint** vous indique s’il s’agit du même certificat ou de plusieurs certificats.
    
5. Si vous avez les entrées SAN recommandées dans notre section Planification, vous êtes bon. Si ce n’est pas le cas, vous devrez demander un nouveau certificat ou plusieurs certificats (selon votre configuration) auprès de votre autorité de certification.
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a>Demander un ou plusieurs nouveaux certificats auprès de votre autorité de certification

1. Une fois que vous avez vérifié les entrées SAN dont vous avez besoin, vous savez que vous avez un seul **certificat (après** avoir vérifié via les étapes ci-dessus) et vous avez appris que vous ne connaissez pas toutes les entrées dont vous avez besoin. Une nouvelle demande de certificat doit être faite à votre ca. Ouvrez votre Skype Entreprise Server PowerShell :
    
   - Pour un SAN de service de découverte automatique manquant (en remplaçant le paramètre -Ca par votre propre chemin d’accès de l’autorité de certification) :
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - Maintenant, si vous avez plusieurs domaines SIP, vous ne pouvez pas utiliser le paramètre AllSipDomain comme dans l’exemple ci-dessus. Vous devez utiliser le paramètre DomainName à la place. Lorsque vous utilisez le paramètre DomainName, vous devez définir le nom de domaine (FQDN) pour les enregistrements lyncdiscoverinternal et lyncdiscover. Par exemple, (en remplaçant le paramètre -Ca par votre propre chemin d’accès à l’autorité de certification) :
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. Ou, après avoir vérifié les entrées SAN dont vous avez besoin, vous avez trouvé que vous avez plusieurs certificats qui ne sont pas toutes les **entrées** dont vous avez besoin. Une nouvelle demande de certificat doit être faite à votre ca. Ouvrez votre Skype Entreprise Server PowerShell :
    
   - Pour un SAN de service de découverte automatique manquant (en remplaçant le paramètre -Ca par votre propre chemin d’accès de l’autorité de certification) :
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - Maintenant, si vous avez plusieurs domaines SIP, vous ne pouvez pas utiliser le paramètre AllSipDomain comme dans l’exemple ci-dessus. Vous devez utiliser le paramètre DomainName à la place. Lorsque vous utilisez le paramètre DomainName, vous devez définir le nom de domaine (FQDN) pour les enregistrements lyncdiscoverinternal et lyncdiscover. Par exemple (en remplaçant le paramètre -Ca par votre propre chemin d’accès à l’autorité de certification) :
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```powershell
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - Une fois que les nouveaux certificats ont été générés par l’ac, vous devez les affecter.
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a>Attribuer des certificats à l’aide Skype Entreprise Server Management Shell

- En fonction de ce que vous avez trouvé dans la section « Ai-je besoin de nouvelles certifications ci-dessus , vous **devez exécuter** l’une des procédures suivantes .
    
  - Si vous avez un certificat unique pour tout (les empreintes sont identiques), vous devez exécuter cette :
    
  ```powershell
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - Si vous avez des certificats différents pour les éléments (les empreintes sont toutes différentes), exécutez-la à la place :
    
  ```powershell
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a>Affichage des certificats dans la console MMC (Microsoft Management Console)

1. Vous avez la possibilité d’examiner vos certificats à l’aide du logiciel en snap-in Certificats pour la MMC. Il vous suffit de taper MMC dans la recherche et il doit apparaître en tant qu’option d’application.
    
2. Pour ajouter le logiciel en un clin d’œil Certificats, vous devez cliquer sur **Fichier, puis** Ajouter/Supprimer un logiciel en un clin d’œil **...** (ou le raccourci clavier **Ctrl+M** fonctionne également). **Les certificats** seront une option dans le volet gauche, sélectionnez-la, puis Compte  d’ordinateur dans la fenêtre, puis **Suivant**.
    
3. Toujours dans la fenêtre pop-up, selon toute probabilité que vous le faites sur l’ordinateur qui est le domicile des certificats que vous devez examiner, laissez la sélection sur l’ordinateur **local** si c’est le cas. Si vous travaillez sur un ordinateur distant, modifiez la bouton d’radio sur **Un** autre ordinateur, puis entrez le nom deqdn de cet ordinateur ou  utilisez le bouton Parcourir pour rechercher cet ordinateur via AD. Après avoir sélectionné l’ordinateur, vous devez cliquer sur Terminer  lorsque vous êtes prêt, puis **OK** pour ajouter le logiciel en snap-in à la MMC.
    
4. Développez **la section Certificats** dans le volet gauche de la MMC. Développez **également le** dossier Personnel, puis sélectionnez **Certificats**. Cela vous permet de voir les certificats dans ce magasin.
    
5. Vous devez localiser le certificat que vous souhaitez afficher, cliquer dessus avec le bouton droit et choisir **Ouvrir**.
    
    > [!NOTE]
    > Comment savoir quel certificat s’agit-il ? Ce doit être le certificat unique affecté à tous les éléments de votre batterie de serveurs, ou vous pouvez avoir plusieurs certificats pour différents éléments, tels que default, Internal Web Services, etc., auquel cas vous devrez peut-être examiner plusieurs certificats. Plusieurs certificats auront la même empreinte numérique. 
  
6. Une fois que vous avez obtenu **l’affichage Certificat** , choisissez **Détails**. Cela vous permet de voir le nom de l’objet du certificat lorsque vous sélectionnez **Objet**, et le nom du sujet affecté et les propriétés associées sont affichés.
    
7. Vous devez également vérifier les entrées de **l’autre nom du** sujet. Vous trouverez une ou plusieurs des informations suivantes :
    
   - Nom du pool ou nom du serveur unique s’il ne s’agit pas d’un pool.
    
   - Nom du serveur à qui le certificat est affecté.
    
   - Enregistrements d’URL simples, généralement meet et dialin.
    
   - Noms externes des services Web et internes des services Web (par exemple, webpool01.contoso.net, webpool01.contoso.com), en fonction des choix effectués dans le Générateur de topologie et les sélections de services Web surchargées.
    
   - S’il est déjà affecté, le lyncdiscover.\<sipdomain\> et lyncdiscoverinternal.\<sipdomain\> enregistrements.
    
     Vous devez vérifier plusieurs certificats si plusieurs certificats vous sont affectés (consultez la remarque ci-dessus).
    
8. Par conséquent, si vous trouvez lyncdiscover.\<sipdomain\> et lyncdiscoverinternal.\<sipdomain\> enregistrements, vous avez déjà configuré cette configuration. Vous pouvez fermer la MMC.
    
9. S’ils ne sont pas affectés, vous devrez soit effectuer une nouvelle demande de certificat (décrite ci-dessus), soit les installer après la demande (nous vous recommandons de suivre l’exemple PowerShell ci-dessus pour cela).
    
## <a name="configure-the-reverse-proxy"></a>Configurer le proxy inverse
<a name="ConfigRP"> </a>

Les étapes ci-dessous ne sont pas destinées à être suivies exactement. En effet, dans les versions précédentes du produit, nous vous avons parcourus, par exemple, en configurant TMG (Threat Management Gateway) et si vous n’utilisiez pas cette version, vous devrez trouver votre propre version à partir de là.
  
TMG n’est plus proposé par Microsoft en tant que produit et si vous devez encore le configurer, vous pouvez examiner les étapes de [Lync Server 2013](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-the-reverse-proxy-for-mobility). Toutefois, les informations suivantes sont destinées à être plus généralement utiles, même s’il n’existe aucun moyen de fournir des étapes de procédure pas à pas spécifiques pour chaque proxy inverse.
  
Nous devons prendre en compte deux éléments principaux :
  
- Allez-vous faire votre première demande de découverte automatique sur HTTPS (ce que nous vous recommandons) ?
    
  - Si vous avez une règle de publication web, vous devez la modifier.
    
  - Si vous n’avez pas encore de règle de publication web, vous devez la créer.
    
- Si vous faites votre première demande de découverte automatique sur HTTP, vous devez également créer ou modifier cette règle.
    
> [!NOTE]
> **Important** Une valeur de délai d’délai proxy est un nombre qui varie d’un déploiement à l’autre. Vous devez surveiller votre déploiement et modifier la valeur pour une expérience de qualité pour les clients. Vous pourrez peut-être définir la valeur sur 200. Si vous prisez en charge les clients mobiles Lync dans votre environnement, vous devez définir la valeur sur 960 pour autoriser les délai d’Office 365 de notification push, dont la valeur de délai d’délai d’utilisation est de 900. Il est très probable que vous de dû augmenter la valeur du délai d’délai pour éviter les déconnexions client lorsque la valeur est trop faible, ou diminuer le nombre si les connexions via le proxy ne se déconnectent pas, mais se désconnectent longtemps après la déconnexion du client. La surveillance et la définition de ce qui est habituel pour votre environnement sont le seul moyen précis de déterminer le paramètre approprié pour cette valeur.
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a>Modifier la règle de publication web existante pour votre SAN de découverte automatique externe et l’URL

1. Ouvrez votre interface de proxy inverse.
    
2. Vous devez localiser votre règle de publication web et choisir l’option Modifier (elle peut se trouver dans un menu ou un onglet, selon votre configuration de proxy inverse).
    
3. Il doit y avoir une zone qui indique à quoi cette règle de publication web s’applique. Vous devez modifier cette règle pour les sites entrants ou les demandes de sites. Vous allez ajouter **une** nouvelle entrée.
    
4. Tapez le nom de votre site de découverte automatique (l’exemple que nous allons utiliser est lyncdiscover.contoso.com), puis cliquez sur **OK** ou **Enregistrer, selon** le format de votre proxy inverse.
    
5. Vous disposez peut-être d’un nouveau certificat avec l’entrée SAN de découverte automatique. Celui-ci doit également être installé et configuré pour être utilisé en fonction des paramètres de votre proxy inverse. N’oubliez pas d’enregistrer tous les paramètres une fois la configuration terminée.
    
6. Si votre proxy inverse dispose **d’une fonctionnalité test** , utilisez-la pour vous assurer que tout fonctionne correctement.
    
7. Maintenant, vous devrez peut-être répéter ces étapes si vous avez un directeur ou un pool directeur dans votre environnement (cela signifie que vous avez une deuxième règle).
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a>Créer une règle de publication web pour l’URL de découverte automatique externe

1. Ouvrez votre interface de proxy inverse.
    
2. Vous devez localiser l’emplacement dans l’interface où vous créez vos règles de publication web,  puis choisir **l’option Nouveau** ou Créer (elle peut se trouver dans un menu ou un onglet, en fonction de votre configuration de proxy inverse). Vous recherchez l’option de création d’une règle de publication web.
    
3. En règle générale, vous devez entrer les informations suivantes :
    
   - **Name** : nom de votre règle
    
   - **Action de** la règle : dans ce cas, il  s’agit d’une règle d’autoriser, vous laissez quelque chose passer par votre proxy inverse.
    
   - La **règle ou** l’option de publication que vous choisissez serait un **site web unique ou un équilibreur de charge**.
    
   - Il doit s’agit **du SSL pour** l’accès externe, choisissez cette option.
    
   - Vous devrez publier un chemin d’accès pour la publication **interne et entrer** le nom deqdn des services web externes sur le programme d’équilibrage de charge de votre pool frontal (ou le nom de groupe du programme d’équilibrage de charge du pool directeur si vous en avez un), par exemple sfb_pool01.contoso.local.
    
   - Vous devez taper **/\\** _ comme chemin d’accès à publier, mais vous devez également _*forward l’en-tête d’hôte d’origine**.
    
   - Il y aura une option **pour les informations** ou les détails des noms publics ou externes. Il s’agit de l’endroit où vous pourrez entrer :
    
   - **Acceptez les demandes**, mais elles doivent être pour le nom de domaine.
    
   - Pour le **nom**, vous devez entrer **lyncdiscover.**\<sipdomain> (il s’agit de l’URL du service de découverte automatique externe). Maintenant, si vous créez une règle pour l’URL des services web externes sur le pool frontal, vous devez taper le nom de domaine final pour les services web externes sur votre pool frontal (par exemple, lyncwebextpool01.contoso.com).
    
   - Il y aura une option **Chemin** d’accès, et vous devrez entrer **/\\*** ici.
    
   - Vous devez sélectionner un **listener SSL** avec votre certificat public à jour.
    
   - **La délégation d’authentification** doit être définie sur **Aucune délégation**, mais l’authentification client directe **doit** être autorisée.
    
   - La règle doit être définie sur **Tous les utilisateurs**.
    
   - Il doit s’agir de toutes les informations dont vous avez besoin pour créer cette règle et vous permettre de continuer.
    
4. Vous devez vous assurer que l’en-tête d’hôte **d’origine** est bien transmis.
    
5. Les ports **du serveur Web** doivent également être définies, vous devez :
    
   - **Les demandes de redirection vers le port HTTP** et le numéro de port doivent être **8080**.
    
   - **Rediriger les demandes vers le port SSL** et le numéro de port doit être **4443**.
    
6. Lorsque tout est configuré, vous devez les enregistrer ou les appliquer, puis tester la règle.
    
### <a name="create-a-web-publishing-rule-for-port-80-optional"></a>Créer une règle de publication web pour le port 80 (facultatif)

1. Ouvrez votre interface de proxy inverse.
    
2. Vous devez localiser l’emplacement dans l’interface où vous créez vos règles de publication web,  puis choisir **l’option Nouveau** ou Créer (elle peut se trouver dans un menu ou un onglet, en fonction de votre configuration de proxy inverse). Vous recherchez l’option de création d’une règle de publication web.
    
3. En règle générale, vous devez entrer les informations suivantes :
    
   - **Name** : nom de votre règle
    
   - **Action de** la règle : dans ce cas, il  s’agit d’une règle d’autoriser, vous laissez quelque chose passer par votre proxy inverse.
    
   - La **règle ou** l’option de publication que vous choisissez serait un **site web unique ou un équilibreur de charge**.
    
   - Il doit s’agit **d’une connexion non sécurisée pour se connecter au serveur Web ou à la batterie de serveurs publié.**
    
   - Vous devrez publier un chemin d’accès pour la publication **interne et entrer** le nom deqdn de l’adresse **IP** ip du programme d’équilibrage de charge de votre pool frontal, par exemple sfb_pool01.contoso.local.
    
   - Vous devez taper **/\\** _ comme chemin d’accès à publier, mais vous devez également _*forward l’en-tête d’hôte d’origine**.
    
   - Il y aura une option **pour les informations** ou les détails des noms publics ou externes. Il s’agit de l’endroit où vous pourrez entrer :
    
   - **Acceptez les demandes**, mais elles doivent être pour le nom de domaine.
    
   - Pour le **nom**, vous devez entrer **lyncdiscover.**\<sipdomain> (il s’agit de l’URL du service de découverte automatique externe).
    
   - Il y aura une option **Chemin** d’accès, et vous devrez entrer **/\\*** ici.
    
   - Vous devez sélectionner un listener web ou autoriser votre proxy inverse à en créer un pour vous.
    
   - **La délégation d’authentification** doit être définie sur **Aucune délégation**, mais l’authentification client directe **ne doit pas** être autorisée.
    
   - La règle doit être définie sur **Tous les utilisateurs**.
    
   - Il doit s’agir de toutes les informations dont vous avez besoin pour créer cette règle et vous permettre de continuer.
    
4. Les ports **du serveur Web** doivent être définies, vous devez :
    
   - **Les demandes de redirection vers le port HTTP** et le numéro de port doivent être **8080**.
    
   - **Rediriger les demandes vers le port SSL** et le numéro de port doit être **4443**.
    
5. Lorsque tout est configuré, vous devez les enregistrer ou les appliquer, puis tester la règle.
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a>Configurer la découverte automatique pour la mobilité avec des déploiements hybrides
<a name="ConfigAutoD"> </a>

Les environnements hybrides Skype Entreprise Server sont des environnements qui combinent un environnement local et un environnement O365. Lorsque vous avez Skype Entreprise Server dans un environnement hybride, le service de découverte automatique doit pouvoir localiser un utilisateur à partir de l’un de ces environnements.
  
Pour que les clients mobiles découvrent l’emplacement d’un utilisateur, le service de découverte automatique doit être configuré avec une nouvelle URL (Uniform Resource Locator). Voici comment procéder :
  
1. Ouvrez Skype Entreprise Server Management Shell.
    
2. Exécutez la liste suivante pour obtenir la valeur de l’attribut **ProxyFQDN** pour votre environnement Skype Entreprise Server:.
    
   ```powershell
   Get-CsHostingProvider
   ```

3. Ensuite, toujours dans la fenêtre d’shell, exécutez :
    
   ```powershell
   Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
   ```

    Où [identity] est remplacé par le nom de domaine de l’espace d’adresses SIP partagé.
    
## <a name="test-your-mobility-deployment"></a>Tester votre déploiement de mobilité
<a name="TestMobility"> </a>

Une fois que vous avez déployé Skype Entreprise Server Mobility Service et Skype Entreprise Server Autodiscover Service, vous devez exécuter une transaction de test pour vous assurer que votre déploiement fonctionne bien. Vous pouvez exécuter **Test-CsUcwaConference** pour tester la capacité de deux utilisateurs à créer, rejoindre et communiquer dans une conférence. Vous aurez besoin de deux utilisateurs (réel ou test) et de leurs informations d’identification complètes pour ce test. Cette commande fonctionne pour les clients Skype Entreprise clients, ainsi que pour les clients Lync Server 2013.
  
Pour les clients Lync Server 2010 sur Skype Entreprise Server 2015, vous devez exécuter **Test-CsMcxP2PIM** pour le test. Vos utilisateurs Lync Server 2010 devront toujours être des utilisateurs réels ou des utilisateurs de test prédéfincis, et vous aurez besoin de leurs informations d’identification de mot de passe.

> [!NOTE]
> La prise en charge de MCX (Mobility Service) pour les clients mobiles hérités n’est plus disponible Skype Entreprise Server 2019. Tous les clients mobiles Skype Entreprise actuellement utilisent déjà l’API UCWA (Unified Communications Web API) pour prendre en charge la messagerie instantanée, la présence et les contacts. Les utilisateurs ayant des clients hérités utilisant MCX devront mettre à niveau vers un client actuel.
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a>Test de la conférence pour Skype Entreprise clients mobiles Lync 2013

1. Log on as a member of the **CsAdministrator** role on any computer where **Skype Entreprise Server Management Shell** and **Ocscore** are installed.
    
2. Démarrez **l Skype Entreprise Server Management Shell** (vous pouvez taper le nom dans la recherche ou aller à **Tous** les programmes et le choisir).
    
3. À partir de la ligne de commande, entrez :
    
   ```powershell
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   Il est également possible de définir des informations d’identification dans un script et de les transmettre à l’cmdlet de test. Nous en avons un exemple ci-dessous.
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a>Test de la conférence pour les clients mobiles Lync 2010

> [!NOTE]
> La prise en charge de MCX (Mobility Service) pour les clients mobiles hérités n’est plus disponible Skype Entreprise Server 2019. Tous les clients mobiles Skype Entreprise actuellement utilisent déjà l’API UCWA (Unified Communications Web API) pour prendre en charge la messagerie instantanée, la présence et les contacts. Les utilisateurs ayant des clients hérités utilisant MCX devront mettre à niveau vers un client actuel.

1. Log on as a member of the **CsAdministrator** role on any computer where **Skype Entreprise Server Management Shell** and **Ocscore** are installed.
    
2. Démarrez **l Skype Entreprise Server Management Shell** (vous pouvez taper le nom dans la recherche ou aller à **Tous** les programmes et le choisir).
    
3. À partir de la ligne de commande, entrez :
    
   ```powershell
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   Il est également possible de définir des informations d’identification dans un script et de les transmettre à l’cmdlet de test. Nous en avons un exemple ci-dessous.
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
   ```

Pour passer en revue les procédures de commande, vous pouvez consulter [Test-CsUcwaConference](/powershell/module/skype/test-csucwaconference) et [Test-CsMcxP2PIM](/powershell/module/skype/test-csmcxp2pim).
  
## <a name="configure-for-push-notifications"></a>Configurer les notifications de type push
<a name="ConfigPush"> </a>

Les notifications Push, sous forme de badges, d’icônes ou d’alertes, peuvent être envoyées à un appareil mobile même lorsque l’application Skype ou Lync est inactive. Mais qu’est-ce que les notifications Push ? Il s’agit d’alertes d’événement, telles qu’une invitation de messagerie instantanée nouvelle ou manquée, ou pour une messagerie vocale reçue. Le service de mobilité Skype Entreprise Server envoie ces notifications au service de notification push Skype Entreprise Server basé sur le cloud, qui envoie ensuite les notifications au service de notifications Push de Microsoft (MSNS) pour les Windows Phone utilisateurs.
  
Cette fonctionnalité est inchangée par rapport à Lync Server 2013, mais si vous avez une Skype Entreprise Server, vous devez :
  
- Pour un serveur Edge Skype Entreprise Server, ajoutez un nouveau fournisseur d’hébergement, Microsoft Skype Entreprise Online, puis définissez la fédération des fournisseurs d’hébergement entre votre organisation et Skype Entreprise Online.
    
- Activez les notifications push en exécutant l’cmdlet **Set-CsPushNotificationConfiguration** . Par défaut, les notifications push sont désactivées.
    
- Testez la configuration de votre fédération et les notifications Push.
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a>Configurer votre serveur Edge Skype Entreprise pour les notifications Push

1. Log on, with an account that’s a member of the **CsAdministrator** role, to a computer where **Skype Entreprise Server Management Shell** and **Ocscore** are installed.
    
2. Démarrez le **Skype Entreprise Server Management Shell**.
    
3. Ajoutez un fournisseur Skype Entreprise Server d’hébergement en ligne.
    
   ```powershell
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   Par exemple :
    
   ```powershell
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > Vous ne pouvez pas avoir plusieurs relations de fédération avec un seul fournisseur d’hébergement. Par exemple, si vous avez déjà mis en place un fournisseur d’hébergement ayant une relation de fédération avec sipfed.online.lync.com, n’ajoutez pas d’autre fournisseur d’hébergement pour celui-ci, même si l’identité du fournisseur d’hébergement est autre que SkypeOnline. 
  
4. Configurer la fédération du fournisseur d’hébergement entre votre organisation et le service de notifications Push sur Skype Entreprise Online. Sur la ligne de commande, vous devez taper :
    
   ```powershell
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a>Activer les notifications Push

1. Log on, with an account that’s a member of the **CsAdministrator** role, to a computer where **Skype Entreprise Server Management Shell** and **Ocscore** are installed.
    
2. Démarrez le **Skype Entreprise Server Management Shell**.
    
3. Activez les notifications Push :
    
   ```powershell
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. Activer la fédération :
     
   ```powershell
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a>Tester la fédération et les notifications Push

1. Log on, with an account that’s a member of the **CsAdministrator** role, to a computer where **Skype Entreprise Server Management Shell** and **Ocscore** are installed.
    
2. Démarrez le **Skype Entreprise Server Management Shell**.
    
3. Testez la configuration de la fédération :
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
   ```

    Par exemple :
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com
   ```

4. Testez vos notifications Push :
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
   ```

    Par exemple :
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com
   ```

## <a name="configure-mobility-policy"></a>Configurer la stratégie de mobilité
<a name="ConfigMob"> </a>

Vous avez la possibilité avec Skype Entreprise Server de déterminer qui peut utiliser votre service de mobilité, appel via le travail, voIP ou vidéo, ainsi que si le WiFi sera requis pour voIP ou vidéo. L’appel via le lieu de travail permet à un utilisateur mobile d’utiliser son numéro de téléphone de travail, au lieu de son numéro de téléphone mobile, lors de l’appel et de la réception d’appels. La personne à l’autre extrémité de la ligne ne verra pas le numéro de téléphone portable de cet utilisateur mobile et elle lui permet d’éviter les frais d’appels sortants. Lorsque voIP et vidéo sont mis en place, les utilisateurs peuvent prendre et effectuer des appels VoIP et vidéo. Les paramètres d’utilisation du WiFi déterminent si l’appareil mobile d’un utilisateur doit utiliser un réseau WiFi sur un réseau de données cellulaires.
  
La mobilité, l’appel via le travail et les fonctionnalités VoIP et vidéo sont toutes activées par défaut. Le paramètre pour exiger le WiFi pour VoIP et la vidéo est désactivé. Un administrateur a la possibilité de modifier cela, globalement, par site ou par utilisateur.
  
Pour pouvoir utiliser les fonctionnalités de mobilité et appel via le travail, les utilisateurs doivent :
  
- Activé pour les Skype Entreprise Server
    
- Activé pour les Voix Entreprise.
    
- Affecté à une stratégie de mobilité dont l’option **EnableMobility** est définie sur **True**.
    
Pour que les utilisateurs puissent utiliser l’appel via le travail, ils doivent également :
  
- Une stratégie de voix dont l’option Activer **la sonnerie simultanée des téléphones** est sélectionnée.
    
- Affecté à une stratégie de mobilité dont **la valeur EnableOutsideVoice** est **définie sur True**.
    
> [!NOTE]
> Les utilisateurs qui ne sont pas activés pour Voix Entreprise peuvent utiliser leur appareil mobile pour effectuer des Skype pour Skype appels VoIP ou participer à des conférences à l’aide du lien Cliquer pour rejoindre sur leur appareil mobile, si les options appropriées sont définies pour la stratégie de voix à qui ils sont associés. Vous y avez plus de détails dans la rubrique PLANIFICATION. 
  
### <a name="modify-global-mobility-policy"></a>Modifier la stratégie de mobilité globale

1. Log on, with an account that’s a member of the **CsAdministrator** role, to a computer where **Skype Entreprise Server Management Shell** and **Ocscore** are installed.
    
2. Démarrez le **Skype Entreprise Server Management Shell**.
    
3. Désactiver globalement l’accès à la mobilité et à l’appel via le travail en tapant :
    
   ```powershell
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > Vous pouvez désactiver l’appel via le travail sans désactiver l’accès à la mobilité. Toutefois, vous ne pouvez pas désactiver la mobilité sans également désactiver l’appel via le travail. 
  
    Pour plus d’informations, [voir Set-CsMobilityPolicy](/powershell/module/skype/set-csmobilitypolicy).
    
### <a name="modify-mobility-policy-by-site"></a>Modifier la stratégie de mobilité par site

1. Log on, with an account that’s a member of the **CsAdministrator** role, to a computer where **Skype Entreprise Server Management Shell** and **Ocscore** are installed.
    
2. Démarrez le **Skype Entreprise Server Management Shell**.
    
3. Vous pouvez créer une stratégie au niveau du site, désactiver voIP et vidéo, activer Le WiFi nécessaire pour l’audio IP et Exiger le WiFi pour la vidéo IP par site. Type :
    
   ```powershell
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    Pour plus [d’informations, ez-vous sur New-CsMobilityPolicy](/powershell/module/skype/new-csmobilitypolicy).
    
### <a name="modify-mobility-policy-by-user"></a>Modifier la stratégie de mobilité par utilisateur

1. Log on, with an account that’s a member of the **CsAdministrator** role, to a computer where **Skype Entreprise Server Management Shell** and **Ocscore** are installed.
    
2. Démarrez le **Skype Entreprise Server Management Shell**.
    
3. Créer des stratégies de mobilité au niveau de l’utilisateur et désactiver la mobilité et l’appel via le travail par utilisateur. Type :
    
   ```powershell
   New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
   ```

    Un autre exemple avec des exemples de données :
    
   ```powershell
   New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity MobileUser1@contoso.com -PolicyName tag:disableOutsideVoice
   ```

    > [!NOTE]
    > Vous pouvez désactiver l’appel via le travail sans désactiver l’accès à la mobilité. Toutefois, vous ne pouvez pas désactiver la mobilité sans également désactiver l’appel via le travail. 
