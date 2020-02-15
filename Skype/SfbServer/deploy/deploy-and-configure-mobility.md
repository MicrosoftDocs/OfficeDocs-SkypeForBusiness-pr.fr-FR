---
title: Déployer et configurer la mobilité pour Skype entreprise Server
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
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: Cet article vous guide tout au long des étapes nécessaires pour configurer une installation de Skype entreprise Server existante afin qu’elle utilise le service de mobilité, ce qui permet à vos appareils mobiles de tirer parti des fonctionnalités de mobilité de Skype entreprise Server.
ms.openlocfilehash: 457eeff39c87f20326d64cc5227745b43e0af5f8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029065"
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server"></a>Déployer et configurer la mobilité pour Skype entreprise Server  
 
Cet article vous guide tout au long des étapes nécessaires pour configurer une installation de Skype entreprise Server existante afin qu’elle utilise le service de mobilité, ce qui permet à vos appareils mobiles de tirer parti des fonctionnalités de mobilité de Skype entreprise Server.
  
Après avoir examiné l’article [plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) , vous devez être prêt à suivre les étapes ci-dessous pour déployer la mobilité dans votre environnement Skype entreprise Server. Les étapes sont les suivantes (et nous les incluons dans ce tableau une liste d’autorisations) :
  
|**Étape**|**Autorisations**|
|:-----|:-----|
|[Créer des enregistrements DNS](deploy-and-configure-mobility.md#CreateDNSRec) <br/> |Admins du domaine  <br/> DNSAdmins  <br/> |
|[Modifier les certificats](deploy-and-configure-mobility.md#ModCerts) <br/> |Administrateur local  <br/> |
|[Configurer le proxy inverse](deploy-and-configure-mobility.md#ConfigRP) <br/> |Administrateur local  <br/> |
|[Configurer la découverte automatique pour la mobilité avec les déploiements hybrides](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |Admins du domaine  <br/> |
|[Tester votre déploiement de mobilité](deploy-and-configure-mobility.md#TestMobility) <br/> |CsAdministrator  <br/> |
|[Configurer les notifications de type push](deploy-and-configure-mobility.md#ConfigPush) <br/> |RtcUniversalServerAdmins  <br/> |
|[Configurer la stratégie de mobilité](deploy-and-configure-mobility.md#ConfigMob) <br/> |CsAdministrator  <br/> |
   
Toutes les sections suivantes contiennent des étapes qui supposent que vous avez lu la rubrique Planning. Si vous êtes déroutant, n’hésitez pas à en consulter les informations.

> [!NOTE]
> La prise en charge de MCX (Mobility service) pour les clients mobiles hérités n’est plus disponible dans Skype entreprise Server 2019. Tous les clients mobiles Skype entreprise actuels utilisent déjà Unified Communications Web API (UCWA) pour prendre en charge la messagerie instantanée, la présence et les contacts. Les utilisateurs avec des clients hérités qui utilisent MCX devront effectuer une mise à niveau vers un client actuel.
  
## <a name="create-dns-records"></a>Créer des enregistrements DNS
<a name="CreateDNSRec"> </a>

Vous disposez peut-être déjà de ces éléments dans le cadre de votre environnement Skype entreprise Server, mais vous devez créer les enregistrements suivants pour que la découverte automatique fonctionne :
  
- Un enregistrement DNS interne pour prendre en charge les utilisateurs mobiles qui se connectent à partir du réseau de votre organisation.
    
- Un enregistrement DNS externe (ou public) pour prendre en charge les utilisateurs mobiles qui se connectent depuis l’extérieur du réseau de votre organisation.
    
Ces enregistrements peuvent être soit des noms (hôtes), soit des enregistrements CNAMe (vous n’avez pas à effectuer les deux à la fois, nous incluons simplement les étapes de tous les éléments ici).
  
### <a name="create-an-internal-dns-cname-record"></a>Créer un enregistrement CNAMe DNS interne

1. Connectez-vous à un serveur DNS de votre réseau qui est membre du groupe **administrateurs du domaine** ou du groupe **DnsAdmins** .
    
2. Cliquez sur **Démarrer**, sélectionnez **Outils d’administration** (il se peut que vous deviez le **Rechercher** s’il n’est pas possible d’utiliser le menu Démarrer), puis cliquez sur **DNS** pour ouvrir le composant logiciel enfichable d’administration DNS.
    
3. Dans le volet de gauche de la fenêtre de la console, vous devez accéder au domaine qui héberge les serveurs frontaux de Skype entreprise Server et développer les **zones de recherche directes** .
    
4. Prenez un moment pour voir les éléments suivants :
    
   - Tout enregistrement A ou AAAA hôte pour votre serveur frontal (standard ou Enterprise) ou un ou plusieurs pools frontaux.
    
   - N’importe quel enregistrement A ou AAAA hôte pour un directeur ou un pool directeur (Configuration facultative que vous pouvez avoir dans votre déploiement).
    
5. Une fois que vous avez noté cela, cliquez avec le bouton droit sur le nom de votre domaine SIP, puis choisissez **Nouvel alias (CNAME)** dans le menu.
    
6. Dans la zone de texte **nom d’alias** , tapez lyncdiscoverinternal pour votre nom d’hôte, pour l’URL du service de découverte automatique interne.
    
7. Dans le **nom de domaine complet (FQDN) de l’hôte de destination**, vous devez taper ou parcourir le nom de domaine complet des services Web internes pour votre pool frontal (ou un serveur frontal unique, ou un pool ou directeur de directeur), identifié à l’étape 4 ci-dessus. Cliquez sur OK lorsque cette entrée est entrée.
    
8. Vous devrez créer un nouvel enregistrement CNAMe de découverte automatique dans la zone de recherche directe pour chaque domaine SIP pris en charge dans votre environnement Skype entreprise Server.
    
### <a name="create-an-external-dns-cname-record"></a>Créer un enregistrement CNAMe DNS externe

1. Ces étapes sont génériques, car nous ne pouvons pas indiquer quel fournisseur DNS public vous pouvez utiliser, mais nous souhaitons toujours vous aider. Connectez-vous à votre fournisseur DNS public à l’aide d’un compte qui pourra y créer de nouveaux enregistrements DNS.
    
2. À ce stade, un domaine SIP doit déjà exister ici pour Skype entreprise Server. Développez la **zone de recherche directe** pour ce domaine SIP, ou ouvrez-la.
    
3. Prenez un moment pour voir les éléments suivants :
    
   - Tout enregistrement A ou AAAA hôte pour votre serveur frontal (standard ou Enterprise) ou un ou plusieurs pools frontaux.
    
   - N’importe quel enregistrement A ou AAAA hôte pour un directeur ou un pool directeur (Configuration facultative que vous pouvez avoir dans votre déploiement).
    
4. Une fois que vous disposez de ces informations, vous devez pouvoir sélectionner une option pour créer un **Nouvel alias (CNAME)**.
    
5. À présent, vous devriez pouvoir entrer un **nom d’alias**, vous devez entrer lyncdiscover ici pour l’URL du service de découverte automatique externe.
    
6. Il doit s’agir d’une zone à entrer dans un **nom de domaine complet (FQDN) pour l’hôte cible**, il doit s’agir du nom de domaine complet de votre pool frontal (ou d’un serveur frontal unique, ou du pool ou directeur de directeur) identifié à l’étape 3 ci-dessus.
    
7. Vous devrez peut-être enregistrer cet emplacement, ou si vous devez créer des enregistrements CNAMe supplémentaires dans la zone de recherche directe de chaque domaine SIP dans votre environnement Skype entreprise Server, vous devez procéder ainsi, mais une fois que vous êtes prêt, enregistrez votre travail.
    
### <a name="create-an-internal-dns-a-record"></a>Créer un enregistrement DNS A interne

1. Connectez-vous à un serveur DNS de votre réseau qui est membre du groupe **administrateurs du domaine** ou du groupe **DnsAdmins** .
    
2. Cliquez sur **Démarrer**, sélectionnez **Outils d’administration** (il se peut que vous deviez le **Rechercher** s’il n’est pas possible d’utiliser le menu Démarrer), puis cliquez sur **DNS** pour ouvrir le composant logiciel enfichable d’administration DNS.
    
3. Dans le volet de gauche de la fenêtre de la console, vous devez accéder au domaine qui héberge les serveurs frontaux de Skype entreprise Server et développer les **zones de recherche directes** .
    
4. Prenez un moment pour voir les éléments suivants :
    
   - Tout enregistrement A ou AAAA hôte pour votre serveur frontal (standard ou Enterprise) ou un ou plusieurs pools frontaux.
    
   - N’importe quel enregistrement A ou AAAA hôte pour un directeur ou un pool directeur (Configuration facultative que vous pouvez avoir dans votre déploiement).
    
5. Une fois que vous avez noté cela, cliquez avec le bouton droit sur le nom de votre domaine SIP, puis sélectionnez **nouvel hôte (A ou AAAA)** dans le menu.
    
6. Dans la zone de texte **nom** , tapez lyncdiscoverinternal pour votre nom d’hôte, pour l’URL du service de découverte automatique interne.
    
7. Dans la zone **adresse IP** , tapez l’adresse IP interne des services Web pour votre pool frontal (ou un serveur frontal unique, ou un pool ou directeur de directeur), identifié à l’étape 4 ci-dessus.
    
8. Une fois cette opération terminée, cliquez sur **Ajouter un hôte**, puis cliquez sur **OK**.
    
9. Vous devrez créer un nouvel enregistrement Autodiscover A ou AAAA dans la zone de recherche directe pour chaque domaine SIP pris en charge dans votre environnement Skype entreprise Server. Pour ce faire, répétez les étapes 6-8 autant de fois que nécessaire.
    
10. Lorsque vous avez fini, cliquez sur **Terminer**.
    
### <a name="create-an-external-dns-a-record"></a>Créer un enregistrement A DNS externe

1. Ces étapes sont génériques, car nous ne pouvons pas indiquer quel fournisseur DNS public vous pouvez utiliser, mais nous souhaitons toujours vous aider. Connectez-vous à votre fournisseur DNS public à l’aide d’un compte qui pourra y créer de nouveaux enregistrements DNS.
    
2. À ce stade, un domaine SIP doit déjà exister ici pour Skype entreprise Server. Développez la **zone de recherche directe** pour ce domaine SIP, ou ouvrez-la.
    
3. Prenez un moment pour voir les éléments suivants :
    
   - Tout enregistrement A ou AAAA hôte pour votre serveur frontal (standard ou Enterprise) ou un ou plusieurs pools frontaux.
    
   - N’importe quel enregistrement A ou AAAA hôte pour un directeur ou un pool directeur (Configuration facultative que vous pouvez avoir dans votre déploiement).
    
4. Une fois que vous disposez de ces informations, vous devez être en mesure de sélectionner une option pour créer un **nouvel hôte a ou AAAA**.
    
5. À présent, vous devriez pouvoir entrer un **nom**, vous devez entrer lyncdiscover ici pour l’URL du service de découverte automatique externe.
    
6. Ensuite, il doit y avoir une zone à saisir dans une **adresse IP**, il doit s’agir de l’adresse IP de votre pool frontal (ou d’un serveur frontal unique, ou d’un pool directeur ou directeur), identifié à l’étape 3 ci-dessus.
    
7. Vous devrez peut-être enregistrer ici, ou si vous avez besoin de créer des enregistrements A ou AAAA supplémentaires dans la zone de recherche directe de chaque domaine SIP pour votre environnement Skype entreprise Server, vous devez procéder ainsi, mais une fois que vous êtes prêt, enregistrez votre travail.
    
## <a name="modify-certificates"></a>Modifier les certificats
<a name="ModCerts"> </a>

Si vous avez des questions sur la planification des certificats, nous avons documenté cela dans notre article [plan for Mobility for Skype for Business Server](../plan-your-deployment/mobility.md) . Une fois que vous avez consulté ce qui suit, nous allons vous présenter les éléments suivants :
  
- Ai-je besoin de nouveaux certificats ?
    
- Demande de nouveaux certificats auprès de votre autorité de certification (CA).
    
- Mise à jour de vos certificats sur place avec les remplacements à l’aide de PowerShell.
    
- Vérification des certificats à l’aide du composant logiciel enfichable Certificats dans la console MMC (Microsoft Management Console).
    
### <a name="do-i-need-new-certificates"></a>Ai-je besoin de nouveaux certificats ?

1. Tout d’abord, il se peut que vous deviez vérifier et voir quels certificats sont en place, et s’ils disposent ou non des entrées dont vous avez besoin. Pour ce faire, vous devez vous connecter à votre serveur Skype entreprise à l’aide d’un compte administrateur local. Pour certaines de ces étapes, il se peut que ce compte doive également disposer de droits sur l’autorité de certification émettrice.
    
2. Ouvrez Skype entreprise Server Management Shell (vous pouvez utiliser la recherche pour le trouver si vous ne l’avez pas épinglée à votre menu Démarrer ou à la barre des tâches).
    
3. Il va être essentiel de savoir quels certificats ont été affectés avant d’ajouter un certificat mis à jour. Par conséquent, à la commande, tapez :
    
   ```powershell
   Get-CsCertificate
   ```

4. Les informations de l’étape 3 vous seront propres. Vous devez le Rechercher pour déterminer si vous avez un certificat unique qui a été affecté à plusieurs éléments, ou si vous avez un certificat différent affecté aux différents composants qui en ont besoin. Le paramètre **use** vous indique le mode d’utilisation d’un certificat et le paramètre d' **empreinte** vous indique s’il s’agit du même certificat ou de plusieurs certificats.
    
5. Si vous avez les entrées SAN recommandées dans notre section planification, vous avez l’habitude. Si ce n’est pas le cas, vous devrez demander un nouveau certificat ou plusieurs certificats (en fonction de votre configuration) auprès de votre autorité de certification.
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a>Demander un nouveau certificat ou des certificats auprès de votre autorité de certification (CA)

1. Une fois que vous avez vérifié les entrées SAN dont vous disposez, vous savez que vous disposez d’un **certificat unique** (après avoir vérifié les étapes ci-dessus), et que vous avez appris que vous n’avez pas toutes les entrées dont vous avez besoin. Une nouvelle demande de certificat doit être effectuée sur votre autorité de certification. Ouvrez votre serveur PowerShell Skype entreprise :
    
   - Pour un SAN de service de découverte automatique manquant (en remplaçant le paramètre-ca par votre propre chemin d’accès de l’autorité de certification) :
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - À présent, si vous avez plusieurs domaines SIP, vous ne pouvez pas utiliser le paramètre AllSipDomain comme dans l’exemple ci-dessus. Vous devez utiliser le paramètre DomainName à la place. Lorsque vous utilisez le paramètre DomainName, vous devez définir le nom de domaine complet (FQDN) pour les enregistrements lyncdiscoverinternal et lyncdiscover. Voici un exemple (remplacement du paramètre-ca par votre propre chemin d’accès à l’autorité de certification) :
    
   ```powershell
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. Ou, une fois que vous avez vérifié les entrées SAN dont vous disposez, vous avez trouvé **plusieurs certificats** qui n’ont pas toutes les entrées dont vous avez besoin. Une nouvelle demande de certificat doit être effectuée sur votre autorité de certification. Ouvrez votre serveur PowerShell Skype entreprise :
    
   - Pour un SAN de service de découverte automatique manquant (en remplaçant le paramètre-ca par votre propre chemin d’accès de l’autorité de certification) :
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - À présent, si vous avez plusieurs domaines SIP, vous ne pouvez pas utiliser le paramètre AllSipDomain comme dans l’exemple ci-dessus. Vous devez utiliser le paramètre DomainName à la place. Lorsque vous utilisez le paramètre DomainName, vous devez définir le nom de domaine complet (FQDN) pour les enregistrements lyncdiscoverinternal et lyncdiscover. Voici quelques exemples (remplacer le paramètre-ca par votre propre chemin d’accès à l’autorité de certification) :
    
   ```powershell
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```powershell
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - Une fois que les nouveaux certificats ont été générés par l’autorité de certification, vous devez les affecter.
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a>Affecter des certificats à l’aide de Skype entreprise Server Management Shell

- En fonction de ce que vous avez trouvé dans la section ai-je besoin de nouvelles certifications ci-dessus, vous devez exécuter l' **un** des éléments suivants.
    
  - Si vous disposez d’un certificat unique pour tous les éléments (les empreintes sont identiques), vous devez exécuter l’élément suivant :
    
  ```powershell
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - Si vous avez des certificats différents pour des éléments (les empreintes sont tous différents), exécutez plutôt cette fonction :
    
  ```powershell
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a>Affichage des certificats dans la console MMC (Microsoft Management Console)

1. Vous avez la possibilité de consulter vos certificats à l’aide du composant logiciel enfichable Certificats pour la console MMC. Il vous suffit de taper MMC dans la recherche et de le faire apparaître comme option d’application.
    
2. Pour ajouter le composant logiciel enfichable Certificats, vous devez cliquer sur **fichier**, puis sur **Ajouter/supprimer un composant logiciel enfichable...** (ou un raccourci clavier **Ctrl + M** fonctionne également). Les **certificats** seront une option dans le volet de gauche, sélectionnez-le, puis **compte d’ordinateur** dans la fenêtre contextuelle, puis cliquez sur **suivant**.
    
3. Toujours dans la fenêtre contextuelle, quelle que soit la probabilité que vous effectuiez cette opération sur l’ordinateur qui est à l’origine des certificats que vous devez consulter, conservez la sélection sur **ordinateur local** si c’est le cas. Si vous travaillez sur un ordinateur distant, modifiez la case d’option sur **un autre ordinateur** , puis entrez le nom de domaine complet de l’ordinateur ou utilisez le bouton **Parcourir** pour rechercher cet ordinateur via ad. Après avoir sélectionné l’ordinateur, vous devez cliquer sur **Terminer** lorsque vous êtes prêt, puis sur **OK** pour ajouter le composant logiciel enfichable à la console MMC.
    
4. Développez la section **certificats** dans le volet de gauche de la console MMC. Développez également le dossier **personnel** , puis sélectionnez **certificats**. Cela vous permet d’afficher les certificats de ce magasin.
    
5. Vous devez rechercher le certificat que vous souhaitez afficher, cliquez dessus avec le bouton droit, puis choisissez **ouvrir**.
    
    > [!NOTE]
    > Comment savoir quel certificat il s’agit ? Il doit s’agir du certificat unique affecté à tous les éléments de votre batterie de serveurs, ou vous pouvez avoir plusieurs certificats pour différentes choses, tels que default, des services Web internes, etc., auquel cas vous devrez peut-être examiner plusieurs certificats. Plusieurs certificats auront la même empreinte. 
  
6. Une fois que vous avez obtenu la vue du **certificat** , choisissez **Détails**. Cela vous permettra d’afficher le nom de l’objet du certificat lorsque vous sélectionnez l’option **objet**, et le nom de l’objet affecté et les propriétés associées sont affichés.
    
7. Vous devrez également vérifier les entrées de l' **autre nom du sujet** . Vous trouverez un ou plusieurs des éléments suivants :
    
   - Nom du pool de ce pool, ou nom de serveur unique s’il ne s’agit pas d’un pool.
    
   - Nom du serveur auquel le certificat est affecté.
    
   - Enregistrements d’URL simples, généralement correspondant à la numérotation.
    
   - Noms externes des services Web et des services Web (par exemple, webpool01.contoso.net, webpool01.contoso.com), en fonction des choix effectués dans le générateur de topologie et des sélections de services Web remplacés.
    
   - S’il est déjà attribué, le lyncdiscover. \<sipdomain\> et lyncdiscoverinternal. \<enregistrements\> sipdomain.
    
     Vous devrez vérifier plusieurs certificats si vous en avez attribué plusieurs (consultez la remarque ci-dessus).
    
8. Par conséquent, si vous trouvez lyncdiscover. \<sipdomain\> et lyncdiscoverinternal. \<enregistrements\> sipdomain, vous avez déjà configuré cette configuration. Vous pouvez fermer la console MMC.
    
9. Si elles ne sont pas affectées, vous devez créer une demande de certificat (décrite ci-dessus) ou les installer après la demande (nous vous recommandons de suivre PowerShell ci-dessus).
    
## <a name="configure-the-reverse-proxy"></a>Configurer le proxy inverse
<a name="ConfigRP"> </a>

Les étapes ci-dessous ne sont pas destinées à être suivies exactement. En effet, dans les versions précédentes du produit, nous aurions pu vous présenter, par exemple, la configuration de la passerelle de gestion des menaces (TMG) et, si vous ne l’avez pas fait, vous devez utiliser votre propre version à partir de là.
  
TMG n’est plus offert par Microsoft en tant que produit, et si vous devez le configurer, vous pouvez consulter les [étapes de Lync Server 2013](https://technet.microsoft.com/library/hh690011%28v=ocs.15%29.aspx). Toutefois, les informations suivantes doivent être plus généralement utiles, même si vous ne pouvez pas fournir des étapes de procédure pas à pas spécifiques pour chaque proxy inverse.
  
Deux éléments principaux sont à prendre en compte :
  
- Allez-vous effectuer votre demande de découverte automatique initiale sur HTTPs (recommandé) ?
    
  - Si vous avez une règle de publication Web, vous devez la modifier.
    
  - Si vous n’avez pas encore de règle de publication Web, vous devez la créer.
    
- Si vous effectuez votre demande de découverte automatique initiale sur HTTP, vous devez également créer ou modifier cette règle.
    
> [!NOTE]
> **Important** Une valeur de délai d’expiration du proxy est un nombre qui varie d’un déploiement à l’autre. Vous devez surveiller votre déploiement et modifier la valeur pour la meilleure expérience pour les clients. Vous pouvez définir la valeur sur 200. Si vous prenez en charge les clients mobiles Lync dans votre environnement, vous devez définir la valeur sur 960 pour autoriser les délais d’expiration des notifications de type transmission à partir d’Office 365, dont la valeur de délai d’expiration est de 900. Il est fort probable que vous deviez augmenter la valeur du délai d’expiration pour éviter que le client se déconnecte lorsque la valeur est trop faible ou réduire le nombre si les connexions par le biais du proxy ne se déconnectent pas bien après la déconnexion du client. La surveillance et la détermination de la configuration habituelle de votre environnement sont la seule façon de déterminer le paramètre approprié pour cette valeur.
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a>Modifier la règle de publication Web existante pour votre SAN de découverte automatique externe et votre URL

1. Ouvrez votre interface de proxy inverse.
    
2. Vous devez localiser votre règle de publication Web, puis choisir l’option modifier (elle peut se trouver sur un menu ou un onglet, en fonction de la configuration de votre proxy inverse).
    
3. Il doit y avoir un domaine qui indique le type d’application de cette règle de publication Web. Vous devez modifier cette règle pour les sites entrants ou les demandes de sites. Vous allez **Ajouter** une nouvelle entrée.
    
4. Tapez le nom de votre site de découverte automatique (l’exemple que nous allons utiliser est lyncdiscover.contoso.com), puis cliquez sur **OK** ou sur **Enregistrer**, selon le format de votre proxy inverse.
    
5. Vous avez peut-être un nouveau certificat qui contient l’entrée SAN de découverte automatique. Celle-ci doit être installée et configurée pour être utilisée conformément aux paramètres de votre proxy inverse. N’oubliez pas d’enregistrer tous les éléments lorsque la configuration est terminée.
    
6. Si votre proxy inverse dispose d’une fonctionnalité de **test** , utilisez-le pour vous assurer que tout fonctionne correctement.
    
7. À présent, vous devrez peut-être répéter ces étapes si vous avez un directeur ou un pool directeur dans votre environnement (cela signifie que vous disposez d’une deuxième règle).
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a>Créer une règle de publication Web pour l’URL de découverte automatique externe

1. Ouvrez votre interface de proxy inverse.
    
2. Vous devez Rechercher l’emplacement dans l’interface dans lequel vous créez vos règles de publication Web, puis choisir l’option **nouveau** ou **créer** (il peut s’agir d’un menu ou d’un onglet, en fonction de votre configuration de proxy inverse). Vous recherchez l’option permettant de créer une règle de publication Web.
    
3. En règle générale, vous devez entrer les informations suivantes :
    
   - **Name**: nom de votre règle
    
   - **Action**de la règle : dans ce cas, il s’agit d’une règle d' **autorisation** , que vous laissez passer par un proxy inverse.
    
   - La règle ou l’option de **publication** que vous choisissez doit être **un seul site Web ou équilibreur de charge**.
    
   - Cela doit être **SSL** pour l’accès externe, choisissez cette option.
    
   - Vous devrez publier un chemin d’accès pour la **publication interne**, et entrer le nom de domaine complet (FQDN) des services Web externes sur le programme d’équilibrage de charge de votre pool frontal (ou le nom de domaine complet de l’équilibreur de charge du pool directeur s’il en existe un), par exemple, sfb_pool01. contoso. local.
    
   - Vous devez taper ** / *** comme chemin d’accès à publier, mais vous devez également **transférer l’en-tête d’hôte d’origine**.
    
   - Il y aura une option pour les détails du **nom public ou externe** ou des informations. Il s’agit de l’endroit où vous pouvez entrer :
    
   - **Accepter les demandes**, mais il doit s’agir du nom de domaine.
    
   - Pour le **nom**, vous devez entrer **lyncdiscover.** <sipdomain>(il s’agit de l’URL du service de découverte automatique externe). À présent, si vous créez une règle pour l’URL des services Web externes sur le pool frontal, vous devez taper le nom de domaine complet (FQDN) des services Web externes sur votre pool frontal (par exemple, lyncwebextpool01.contoso.com).
    
   - Il y aura une option **path** , et vous devrez entrer ** / *** ici.
    
   - Vous devrez sélectionner un **écouteur SSL** avec votre certificat public à jour.
    
   - La **délégation de l’authentification** doit être définie sur **aucune délégation**, mais l’authentification client directe **doit** être autorisée.
    
   - La règle doit être définie sur **tous les utilisateurs**.
    
   - Il doit s’agir de toutes les informations dont vous avez besoin pour créer cette règle et vous permettre de continuer.
    
4. Vous devez vous assurer que l' **en-tête d’hôte d’origine** est transféré.
    
5. Les ports du **serveur Web** devront également être définis, vous devrez effectuer les opérations suivantes :
    
   - **Rediriger les demandes vers le port http** et le numéro de port doit être **8080**.
    
   - **Rediriger les demandes vers le port SSL** et le numéro de port doit être **4443**.
    
6. Lorsque tout est configuré, vous devez enregistrer ou appliquer ces éléments, puis vous souhaitez tester la règle.
    
### <a name="create-a-web-publishing-rule-for-port-80-optional"></a>Créer une règle de publication Web pour le port 80 (facultatif)

1. Ouvrez votre interface de proxy inverse.
    
2. Vous devez Rechercher l’emplacement dans l’interface dans lequel vous créez vos règles de publication Web, puis choisir l’option **nouveau** ou **créer** (il peut s’agir d’un menu ou d’un onglet, en fonction de votre configuration de proxy inverse). Vous recherchez l’option permettant de créer une règle de publication Web.
    
3. En règle générale, vous devez entrer les informations suivantes :
    
   - **Name**: nom de votre règle
    
   - **Action**de la règle : dans ce cas, il s’agit d’une règle d' **autorisation** , que vous laissez passer par un proxy inverse.
    
   - La règle ou l’option de **publication** que vous choisissez doit être **un seul site Web ou équilibreur de charge**.
    
   - Cela doit être une **connexion non sécurisée pour la connexion au serveur Web publié ou à la batterie de serveurs**.
    
   - Vous allez devoir publier un chemin d’accès pour la **publication interne**, et entrez le nom de domaine complet (FQDN) de l' **adresse IP virtuelle** de l’équilibreur de charge de votre pool frontal, par exemple, sfb_pool01. contoso. local.
    
   - Vous devez taper ** / *** comme chemin d’accès à publier, mais vous devez également **transférer l’en-tête d’hôte d’origine**.
    
   - Il y aura une option pour les détails du **nom public ou externe** ou des informations. Il s’agit de l’endroit où vous pouvez entrer :
    
   - **Accepter les demandes**, mais il doit s’agir du nom de domaine.
    
   - Pour le **nom**, vous devez entrer **lyncdiscover.** <sipdomain>(il s’agit de l’URL du service de découverte automatique externe).
    
   - Il y aura une option **path** , et vous devrez entrer ** / *** ici.
    
   - Vous devrez sélectionner un port d’écoute Web ou autoriser votre proxy inverse à en créer un pour vous.
    
   - La **délégation de l’authentification** doit être définie sur **aucune délégation**, mais l’authentification client directe ne **doit pas** être autorisée.
    
   - La règle doit être définie sur **tous les utilisateurs**.
    
   - Il doit s’agir de toutes les informations dont vous avez besoin pour créer cette règle et vous permettre de continuer.
    
4. Les ports de **serveur Web** doivent être définis, vous devez effectuer les opérations suivantes :
    
   - **Rediriger les demandes vers le port http** et le numéro de port doit être **8080**.
    
   - **Rediriger les demandes vers le port SSL** et le numéro de port doit être **4443**.
    
5. Lorsque tout est configuré, vous devez enregistrer ou appliquer ces éléments, puis vous souhaitez tester la règle.
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a>Configurer la découverte automatique pour la mobilité avec les déploiements hybrides
<a name="ConfigAutoD"> </a>

Les environnements hybrides dans Skype entreprise Server sont des environnements qui combinent un environnement local et un environnement O365. Lorsque vous utilisez Skype entreprise Server dans un environnement hybride, le service de découverte automatique doit pouvoir localiser un utilisateur dans l’un de ces environnements.
  
Pour permettre aux clients mobiles de découvrir où se trouve un utilisateur, le service de découverte automatique doit être configuré avec une nouvelle URL (Uniform Resource Locator). Voici comment procéder :
  
1. Ouvrez Skype entreprise Server Management Shell.
    
2. Exécutez la commande suivante pour obtenir la valeur de l’attribut **ProxyFQDN** pour votre environnement Skype entreprise Server :
    
   ```powershell
   Get-CsHostingProvider
   ```

3. Ensuite, dans la fenêtre du shell, exécutez la commande suivante :
    
   ```powershell
   Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
   ```

    Où [identity] est remplacé par le nom de domaine de l’espace d’adresses SIP partagé.
    
## <a name="test-your-mobility-deployment"></a>Tester votre déploiement de mobilité
<a name="TestMobility"> </a>

Une fois que vous avez déployé Skype for Business Server Mobility service et Skype for Business Server Autodiscover Service, vous pouvez exécuter une transaction de test pour vous assurer que votre déploiement fonctionne correctement. Vous pouvez exécuter **test-CsUcwaConference** pour tester la capacité de deux utilisateurs à créer, rejoindre et communiquer dans une conférence. Vous aurez besoin de deux utilisateurs (réel ou test) et de leurs informations d’identification complètes pour effectuer ce test. Cette commande fonctionne pour les clients Skype entreprise, ainsi que pour les clients Lync Server 2013.
  
Pour les clients Lync Server 2010 sur Skype entreprise Server 2015, vous devez exécuter **test-CsMcxP2PIM** pour tester. Vos utilisateurs de Lync Server 2010 devront toujours être des utilisateurs réels ou des utilisateurs de test prédéfinis, et vous aurez besoin de leurs informations d’identification de mot de passe.

> [!NOTE]
> La prise en charge de MCX (Mobility service) pour les clients mobiles hérités n’est plus disponible dans Skype entreprise Server 2019. Tous les clients mobiles Skype entreprise actuels utilisent déjà Unified Communications Web API (UCWA) pour prendre en charge la messagerie instantanée, la présence et les contacts. Les utilisateurs avec des clients hérités qui utilisent MCX devront effectuer une mise à niveau vers un client actuel.
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a>Tester la Conférence pour les clients mobiles Skype entreprise et Lync 2013

1. Ouvrez une session en tant que membre du rôle **CsAdministrator** sur un ordinateur sur lequel **Skype entreprise Server Management Shell** et **OCSCore** sont installés.
    
2. Démarrez **Skype entreprise Server Management Shell** (vous pouvez taper le nom dans la recherche ou accéder à **tous les programmes** et sélectionnez-le).
    
3. Sur la ligne de commande, entrez :
    
   ```powershell
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   Il est également possible de définir des informations d’identification dans un script et de les transmettre à la cmdlet Test. Nous avons un exemple de ce qui suit.
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a>Conférence de test pour les clients mobiles Lync 2010

> [!NOTE]
> La prise en charge de MCX (Mobility service) pour les clients mobiles hérités n’est plus disponible dans Skype entreprise Server 2019. Tous les clients mobiles Skype entreprise actuels utilisent déjà Unified Communications Web API (UCWA) pour prendre en charge la messagerie instantanée, la présence et les contacts. Les utilisateurs avec des clients hérités qui utilisent MCX devront effectuer une mise à niveau vers un client actuel.

1. Ouvrez une session en tant que membre du rôle **CsAdministrator** sur un ordinateur sur lequel **Skype entreprise Server Management Shell** et **OCSCore** sont installés.
    
2. Démarrez **Skype entreprise Server Management Shell** (vous pouvez taper le nom dans la recherche ou accéder à **tous les programmes** et sélectionnez-le).
    
3. Sur la ligne de commande, entrez :
    
   ```powershell
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   Il est également possible de définir des informations d’identification dans un script et de les transmettre à la cmdlet Test. Nous avons un exemple de ce qui suit.
    
   ```powershell
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
   ```

Pour revoir les procédures de commande, vous pouvez consulter [test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) et [test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps).
  
## <a name="configure-for-push-notifications"></a>Configurer les notifications de type push
<a name="ConfigPush"> </a>

Les notifications de type diffuser, sous la forme de badges, d’icônes ou d’alertes, peuvent être envoyées à un appareil mobile même lorsque l’application Skype ou Lync est inactive. Mais que sont les notifications de type transmission ? Il s’agit d’alertes d’événement, comme une invitation de messagerie instantanée nouvelle ou manquée, ou pour une messagerie vocale reçue. Le service de mobilité Skype entreprise Server envoie ces notifications au service de notifications poussés de Skype entreprise Server basé sur le Cloud, qui envoie ensuite les notifications au service de notifications Microsoft (MSNS) pour les utilisateurs de Windows Phone.
  
Cette fonctionnalité est identique à celle de Lync Server 2013, mais si vous disposez d’un serveur Skype entreprise, vous devez effectuer les opérations suivantes :
  
- Pour un serveur Edge Skype entreprise Server, ajoutez un nouveau fournisseur d’hébergement, Microsoft Skype entreprise Online, puis configurez la Fédération des fournisseurs d’hébergement entre votre organisation et Skype entreprise online.
    
- Activez les notifications de type transmission en exécutant la cmdlet **Set-CsPushNotificationConfiguration** . Par défaut, les notifications push sont désactivées.
    
- Testez la configuration de votre Fédération et les notifications de transmission.
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a>Configuration de votre serveur Microsoft Skype entreprise Edge pour les notifications de type transmission

1. Ouvrez une session avec un compte qui est membre du rôle **CsAdministrator** sur un ordinateur sur lequel **Skype for Business Server Management Shell** et **OCSCore** sont installés.
    
2. Démarrez **Skype entreprise Server Management Shell**.
    
3. Ajoutez un fournisseur d’hébergement Skype entreprise Server.
    
   ```powershell
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   Par exemple :
    
   ```powershell
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > Vous ne pouvez pas avoir plus d’une relation de Fédération avec un seul fournisseur d’hébergement. Par conséquent, si vous avez déjà configuré un fournisseur d’hébergement qui a une relation de Fédération avec sipfed.online.lync.com, n’ajoutez pas un autre fournisseur d’hébergement pour lui, même si l’identité du fournisseur d’hébergement est différente de SkypeOnline. 
  
4. Configurez la Fédération des fournisseurs d’hébergement entre votre organisation et le service de notifications par transmission Skype entreprise online. Sur la ligne de commande, vous devez taper :
    
   ```powershell
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a>Activer les notifications de type transmission

1. Ouvrez une session avec un compte qui est membre du rôle **CsAdministrator** sur un ordinateur sur lequel **Skype for Business Server Management Shell** et **OCSCore** sont installés.
    
2. Démarrez **Skype entreprise Server Management Shell**.
    
3. Activer les notifications de type transmission :
    
   ```powershell
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. Activer la Fédération :
     
   ```powershell
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a>Fédération de test et notifications de type transmission

1. Ouvrez une session avec un compte qui est membre du rôle **CsAdministrator** sur un ordinateur sur lequel **Skype for Business Server Management Shell** et **OCSCore** sont installés.
    
2. Démarrez **Skype entreprise Server Management Shell**.
    
3. Testez la configuration de la Fédération :
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
   ```

    Par exemple :
    
   ```powershell
   Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com
   ```

4. Testez vos notifications d’envoi :
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
   ```

    Par exemple :
    
   ```powershell
   Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com
   ```

## <a name="configure-mobility-policy"></a>Configurer la stratégie de mobilité
<a name="ConfigMob"> </a>

Vous avez la possibilité de contacter Skype entreprise Server pour déterminer qui peut utiliser votre service de mobilité, appeler via le bureau, une voix sur IP (VoIP) ou une vidéo, et si WiFi sera requis pour la voix ou la vidéo. Appel via le bureau permet à un utilisateur mobile d’utiliser son numéro de téléphone professionnel au lieu de son numéro de téléphone mobile lors de l’envoi et de la réception d’appels. La personne à l’autre bout de la ligne ne verra pas le numéro de téléphone portable de l’utilisateur mobile, et elle permettra à l’utilisateur d’envoyer des frais d’appels sortants. Lors de la configuration de VoIP et de vidéo, les utilisateurs peuvent prendre et effectuer des appels VoIP et vidéo. Les paramètres de l’utilisation WiFi déterminent si l’appareil mobile d’un utilisateur doit utiliser un réseau WiFi via un réseau de données cellulaires.
  
La mobilité, l’appel via le bureau et les fonctionnalités VoIP et vidéo sont toutes activées par défaut. Le paramètre pour exiger WiFi pour VoIP et vidéo est désactivé. Un administrateur a la possibilité de le modifier, de manière globale, par site ou par utilisateur.
  
Pour pouvoir utiliser les fonctionnalités de mobilité et d’appel via le bureau, les utilisateurs doivent être :
  
- Activé pour Skype entreprise Server
    
- Activé pour voix entreprise.
    
- Affectation d’une stratégie de mobilité dont l’option **EnableMobility** a la valeur **true**.
    
Pour que les utilisateurs puissent utiliser l’appel via le bureau, ils doivent également être :
  
- Affectation d’une stratégie de voix pour laquelle l’option **activer la sonnerie simultanée de téléphones** est sélectionnée.
    
- Affectation d’une stratégie de mobilité dont la valeur de **EnableOutsideVoice** est définie sur **true**.
    
> [!NOTE]
> Les utilisateurs qui ne sont pas activés pour voix entreprise peuvent utiliser leur appareil mobile pour passer des appels VoIP Skype à Skype ou participer à des conférences à l’aide du lien Cliquer pour rejoindre les appareils mobiles, si les options appropriées sont définies pour la stratégie de voix à laquelle ils sont associés. avec. Vous trouverez plus de détails dans la rubrique planification. 
  
### <a name="modify-global-mobility-policy"></a>Modifier la stratégie de mobilité globale

1. Ouvrez une session avec un compte qui est membre du rôle **CsAdministrator** sur un ordinateur sur lequel **Skype for Business Server Management Shell** et **OCSCore** sont installés.
    
2. Démarrez **Skype entreprise Server Management Shell**.
    
3. Désactivez l’accès à la mobilité et appelez via le Bureau de façon globale en tapant :
    
   ```powershell
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > Vous pouvez désactiver l’appel via le bureau sans désactiver l’accès à la mobilité. Mais vous ne pouvez pas désactiver la mobilité sans désactiver l’appel via le bureau. 
  
    Pour plus d’informations, consultez [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).
    
### <a name="modify-mobility-policy-by-site"></a>Modifier la stratégie de mobilité par site

1. Ouvrez une session avec un compte qui est membre du rôle **CsAdministrator** sur un ordinateur sur lequel **Skype for Business Server Management Shell** et **OCSCore** sont installés.
    
2. Démarrez **Skype entreprise Server Management Shell**.
    
3. Vous pouvez créer une stratégie au niveau du site, désactiver VoIP et la vidéo, activer l’utilisation de WiFi pour l’audio IP et exiger la vidéo Wi-Fi pour IP par site. Type :
    
   ```powershell
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    Pour plus d’informations, consultez la rubrique [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).
    
### <a name="modify-mobility-policy-by-user"></a>Modifier la stratégie de mobilité par utilisateur

1. Ouvrez une session avec un compte qui est membre du rôle **CsAdministrator** sur un ordinateur sur lequel **Skype for Business Server Management Shell** et **OCSCore** sont installés.
    
2. Démarrez **Skype entreprise Server Management Shell**.
    
3. Créez des stratégies de mobilité au niveau de l’utilisateur et désactivez la mobilité et l’appel via le bureau par utilisateur. Type :
    
   ```powershell
   New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
   ```

    Un autre exemple avec des exemples de données :
    
   ```powershell
   New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity MobileUser1@contoso.com -PolicyName tag:disableOutsideVoice
   ```

    > [!NOTE]
    > Vous pouvez désactiver l’appel via le bureau sans désactiver l’accès à la mobilité. Mais vous ne pouvez pas désactiver la mobilité sans désactiver l’appel via le bureau. 
  

