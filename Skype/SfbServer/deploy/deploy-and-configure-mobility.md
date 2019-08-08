---
title: Déploiement et configuration de la mobilité pour Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: Cet article vous guide dans la procédure de configuration d’une installation de Skype entreprise Server existante pour utiliser le service de mobilité et permettre à vos appareils mobiles de profiter des fonctionnalités de mobilité de Skype entreprise Server.
ms.openlocfilehash: 910e23e8aec18d36c3a7e4bda9e97828fb498802
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234573"
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server"></a>Déploiement et configuration de la mobilité pour Skype entreprise Server  
 
Cet article vous guide dans la procédure de configuration d’une installation de Skype entreprise Server existante pour utiliser le service de mobilité et permettre à vos appareils mobiles de profiter des fonctionnalités de mobilité de Skype entreprise Server.
  
Après avoir consulté le [plan de mobilité pour l’article Skype entreprise Server](../plan-your-deployment/mobility.md) , vous devez être prêt à suivre les étapes ci-dessous pour déployer la mobilité dans votre environnement Skype entreprise Server. Voici les étapes à suivre (avec une liste des autorisations incluse dans le tableau) :
  
|**Phase**|**Autorisations**|
|:-----|:-----|
|[Créer des enregistrements DNS](deploy-and-configure-mobility.md#CreateDNSRec) <br/> |DomainAdmins  <br/> DNSAdmins  <br/> |
|[Modifier les certificats](deploy-and-configure-mobility.md#ModCerts) <br/> |Administrateur local  <br/> |
|[Configurer le proxy inverse](deploy-and-configure-mobility.md#ConfigRP) <br/> |Administrateur local  <br/> |
|[Configurer la découverte automatique pour la mobilité avec les déploiements hybrides](deploy-and-configure-mobility.md#ConfigAutoD) <br/> |DomainAdmins  <br/> |
|[Tester votre déploiement de mobilité](deploy-and-configure-mobility.md#TestMobility) <br/> |CsAdministrator  <br/> |
|[Configurer les notifications push](deploy-and-configure-mobility.md#ConfigPush) <br/> |RtcUniversalServerAdmins  <br/> |
|[Configurer la stratégie de mobilité](deploy-and-configure-mobility.md#ConfigMob) <br/> |CsAdministrator  <br/> |
   
Toutes les sections suivantes comprennent des étapes qui impliquent que vous ayez parcouru la rubrique concernant la planification. En cas de doute, n'hésitez pas à consulter les informations fournies ici.

> [!NOTE]
> La prise en charge de MCX (service de mobilité) pour les clients mobiles hérités n’est plus disponible dans Skype entreprise Server 2019. Tous les clients mobiles Skype entreprise actuels utilisent déjà UCWA (Unified Communications Web API) pour la prise en charge de la messagerie instantanée, de la présence et des contacts. Les utilisateurs des clients hérités utilisant MCX doivent effectuer une mise à niveau vers un client actuel.
  
## <a name="create-dns-records"></a>Créer des enregistrements DNS
<a name="CreateDNSRec"> </a>

Vous pouvez déjà disposer de ces éléments dans le cadre de votre environnement Skype entreprise Server, mais vous devez créer les enregistrements suivants pour que la découverte automatique fonctionne:
  
- un enregistrement DNS interne afin de prendre en charge les utilisateurs mobiles qui se connectent depuis le réseau de votre organisation ;
    
- un enregistrement DNS externe (ou public) afin de prendre en charge les utilisateurs mobiles qui se connectent depuis le réseau de votre organisation.
    
Ces enregistrements sont soit des enregistrements de noms (d'hôte) A, soit des enregistrements CNAME (vous n'avez pas à créer ces deux enregistrements, mais nous décrivons ici toutes les étapes pour les deux types d'enregistrement).
  
### <a name="create-an-internal-dns-cname-record"></a>Créer un enregistrement CNAME DNS interne

1. Ouvrez une session sur un serveur DNS de votre réseau qui est membre du groupe **Administrateurs du domaine** ou du groupe **DnsAdmins**.
    
2. Cliquez sur **Démarrer**, Sélectionnez **Outils d’administration ** (vous devrez peut-être **Rechercher ** l'option si elle n'existe pas dans le menu Démarrer), puis cliquez sur **DNS** pour ouvrir le composant logiciel enfichable d'administration DNS.
    
3. Dans le volet gauche de la fenêtre de la console, vous devez vous rendre sur le domaine qui est destiné aux serveurs frontaux de Skype entreprise Server et étendre les **zones de recherche directe** .
    
4. Prenez un moment pour vérifiez lequel des enregistrements suivants vous avez :
    
   - Un ou plusieurs enregistrements d’hôte A ou AAAA pour votre serveur frontal (standard ou entreprise) ou le ou les pools front-end.
    
   - Tout enregistrement d’hôte A ou AAAA d’un directeur ou d’un pool de réalisateur (Configuration facultative éventuellement disponible dans votre déploiement).
    
5. Une fois l'information vérifiée, cliquez avec le bouton droit de la souris sur votre nom de domaine SIP, puis sélectionnez **Nouvel alias (CNAME)** dans le menu.
    
6. Dans la zone **Nom de l’alias**, saisissez le nom d’hôte correspondant à l’URL de service interne de découverte automatique : lyncdiscoverinternal.
    
7. Dans le **nom de domaine complet (FQDN pour l’hôte cible**), vous devez taper ou parcourir le nom de domaine complet (FQDN) des services Web interne pour votre liste frontale (ou un serveur frontal ou un réalisateur), comme indiqué à l’étape 4 ci-dessus. Cliquez sur Entrée une fois le nom saisi.
    
8. Vous devez créer un enregistrement CNAMe de découverte automatique dans la zone de recherche directe pour chaque domaine SIP pris en charge dans votre environnement Skype entreprise Server.
    
### <a name="create-an-external-dns-cname-record"></a>Créer un enregistrement CNAME DNS externe

1. Ces étapes sont génériques, car nous ne pouvons pas déterminer quel fournisseur DNS public vous utilisez, mais elles pourront toujours vous être utiles. Connectez-vous à votre fournisseur DNS public avec un compte qui vous permettra de créer ici de nouveaux enregistrements DNS.
    
2. À ce moment-là, un domaine SIP doit déjà exister pour Skype entreprise Server. Développez la **zone de recherche directe** pour ce domaine SIP, ou procédez à son ouverture.
    
3. Prenez un moment pour vérifiez lequel des enregistrements suivants vous avez :
    
   - Un ou plusieurs enregistrements d’hôte A ou AAAA pour votre serveur frontal (standard ou entreprise) ou le ou les pools front-end.
    
   - Tout enregistrement d’hôte A ou AAAA d’un directeur ou d’un pool de réalisateur (Configuration facultative éventuellement disponible dans votre déploiement).
    
4. Une fois que vous avez vérifié l'information, vous devriez pouvoir sélectionner une option pour créer un **Nouvel alias (CNAME)**.
    
5. Vous devriez maintenant pouvoir saisir un **Nom d'alias**. Saisissez ensuite lyncdiscover en tant qu'URL de service interne de découverte automatique.
    
6. À présent, il devrait y avoir une zone à entrer dans un nom de domaine complet (FQDN) **pour l’hôte cible**, il doit s’agir du nom de domaine complet (FQDN) du pool frontal (ou d’un serveur frontal ou réalisateur), identifié à l’étape 3 ci-dessus.
    
7. Vous devrez peut-être enregistrer cet emplacement ou, si vous avez besoin de créer des enregistrements CNAMe supplémentaires dans la zone de recherche directe de chaque domaine SIP de votre environnement Skype entreprise Server, procédez ainsi, mais lorsque vous serez prêt, enregistrez votre travail.
    
### <a name="create-an-internal-dns-a-record"></a>Créer un enregistrement A DNS interne

1. Ouvrez une session sur un serveur DNS de votre réseau qui est membre du groupe **Administrateurs du domaine** ou du groupe **DnsAdmins**.
    
2. Cliquez sur **Démarrer**, Sélectionnez **Outils d’administration ** (vous devrez peut-être **Rechercher ** l'option si elle n'existe pas dans le menu Démarrer), puis cliquez sur **DNS** pour ouvrir le composant logiciel enfichable d'administration DNS.
    
3. Dans le volet gauche de la fenêtre de la console, vous devez vous rendre sur le domaine qui est destiné aux serveurs frontaux de Skype entreprise Server et étendre les **zones de recherche directe** .
    
4. Prenez un moment pour vérifiez lequel des enregistrements suivants vous avez :
    
   - Un ou plusieurs enregistrements d’hôte A ou AAAA pour votre serveur frontal (standard ou entreprise) ou le ou les pools front-end.
    
   - Tout enregistrement d’hôte A ou AAAA d’un directeur ou d’un pool de réalisateur (Configuration facultative éventuellement disponible dans votre déploiement).
    
5. Une fois l'information vérifiée, cliquez avec le bouton droit de la souris sur votre nom de domaine SIP, puis sélectionnez **Nouvel hôte (A ou AAAA)** dans le menu.
    
6. Dans la zone **Nom**, saisissez le nom d’hôte correspondant à l’URL de service interne de découverte automatique : lyncdiscoverinternal.
    
7. Dans la zone de saisie de l' **adresse IP** , tapez l’adresse IP des services Web internes de votre pool frontal (ou un serveur frontal ou un réalisateur), identifié à l’étape 4 ci-dessus.
    
8. Une fois terminé, cliquez sur **Ajouter un hôte**, puis cliquez sur **OK**.
    
9. Vous devez créer un nouvel enregistrement de découverte automatique A ou AAAA dans la zone de recherche directe pour chaque domaine SIP pris en charge dans votre environnement Skype entreprise Server. Pour ce faire, répétez les étapes 6 à 8 autant de fois que nécessaire.
    
10. Une fois l'opération terminée, cliquez sur **Terminé**.
    
### <a name="create-an-external-dns-a-record"></a>Créer un enregistrement A DNS externe

1. Ces étapes sont génériques, car nous ne pouvons pas déterminer quel fournisseur DNS public vous utilisez, mais elles pourront toujours vous être utiles. Connectez-vous à votre fournisseur DNS public avec un compte qui vous permettra de créer ici de nouveaux enregistrements DNS.
    
2. À ce moment-là, un domaine SIP doit déjà exister pour Skype entreprise Server. Développez la **zone de recherche directe** pour ce domaine SIP, ou procédez à son ouverture.
    
3. Prenez un moment pour vérifiez lequel des enregistrements suivants vous avez :
    
   - Un ou plusieurs enregistrements d’hôte A ou AAAA pour votre serveur frontal (standard ou entreprise) ou le ou les pools front-end.
    
   - Tout enregistrement d’hôte A ou AAAA d’un directeur ou d’un pool de réalisateur (Configuration facultative éventuellement disponible dans votre déploiement).
    
4. Une fois que vous avez vérifié l'information, vous devriez être capable de sélectionner une option pour créer un **Nouvel hôte A ou AAAA)**.
    
5. Vous devriez maintenant pouvoir saisir un **Nom**. Saisissez ensuite lyncdiscover en tant qu'URL de service interne de découverte automatique.
    
6. Ensuite, il devrait y avoir une zone à entrer dans une **adresse IP**, il doit s’agir de l’adresse IP de votre pool frontal (ou d’un serveur frontal unique ou du réalisateur), identifié à l’étape 3 ci-dessus.
    
7. Vous devrez peut-être enregistrer cet emplacement ou, si vous avez besoin de créer des enregistrements A ou AAAA supplémentaires dans la zone de recherche directe de chaque domaine SIP pour votre environnement Skype entreprise Server, vous devez le faire, mais une fois que vous êtes prêt, enregistrez votre travail.
    
## <a name="modify-certificates"></a>Modifier les certificats
<a name="ModCerts"> </a>

Si vous avez des questions sur la planification des certificats, nous avons documenté le [projet dans notre plan de mobilité pour Skype entreprise Server](../plan-your-deployment/mobility.md) . Une fois que vous avez examiné ce qui suit, nous vous guidons à travers les étapes suivantes:
  
- Dois-je obtenir de nouveaux certificats ?
    
- Demande de nouveaux certificats auprès de votre autorité de certification (CA).
    
- Mise à jour sur site de certificats avec les remplacements à l'aide de PowerShell.
    
- Vérification des certificats à l’aide du composant logiciel enfichable Certificats dans Microsoft Management Console (MMC).
    
### <a name="do-i-need-new-certificates"></a>Dois-je obtenir de nouveaux certificats ?

1. Vous devez d'abord vérifier quels certificats sont en place et s'ils disposent ou non des entrées dont vous avez besoin. Pour ce faire, vous devez vous connecter à Skype entreprise Server à l’aide d’un compte d’administrateur local. Ce compte doit également disposer des autorisations d'accès à l'autorité de certification (CA) émettrice pour effectuer certaines de ces étapes.
    
2. Ouvrez Skype entreprise Server Management Shell (vous pouvez utiliser la recherche pour le rechercher si vous n’avez pas épinglé le menu Démarrer ou la barre des tâches).
    
3. Vous devrez absolument savoir quels certificats ont été affectés avant de pouvoir ajouter un certificat mis à jour. À partir de la ligne de commande, saisissez ce qui suit :
    
   ```
   Get-CsCertificate
   ```

4. Les informations fournies à partir de l'étape 3 vous seront spécifiques. Vous devez les vérifier afin de déterminer si vous disposez d'un certificat unique ayant été affecté à plusieurs éléments, ou si vous disposez d'un autre certificat affecté pour les différents composants qui en ont besoin. Le paramètre **Utiliser** vous permettra de savoir de quelle manière un certificat est utilisé et le paramètre **Thumbprint** vous permettra de savoir s'il s'agit du même certificat ou de plusieurs certificats.
    
5. Si vous disposez des entrées SAN recommandées dans votre section Planification, vous n'avez rien à faire. Sinon, vous devrez demander un nouveau certificat ou plusieurs certificats (en fonction de votre configuration) auprès de votre autorité de certification.
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a>Demander un nouveau certificat ou de nouveaux certificats auprès de votre autorité de certification (CA)

1. Après avoir vérifié les entrées SAN dont vous disposez, vous savez que vous avez un **certificat unique** (la vérification ayant été effectuée en suivant la procédure décrite précédemment) et vous savez que vous ne disposez pas de toutes les entrées dont vous avez besoin. Une nouvelle demande de certificat doit être effectuée auprès de votre autorité de certification. Ouvrez votre PowerShell Skype entreprise Server:
    
   - Pour un SAN de service de découverte automatique (en remplaçant le paramètre -Ca par votre propre chemin d'accès à l'autorité de certification) :
    
   ```
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - À présent, si vous avez plusieurs domaines SIP, vous ne pouvez pas utiliser le paramètre AllSipDomain comme dans l’exemple ci-dessus. Vous devrez plutôt utiliser le paramètre DomainName. De plus, lorsque vous utilisez le paramètre DomainName, vous devez définir le nom de domaine complet pour les enregistrements lyncdiscoverinternal et lyncdiscover. En voici un exemple (en remplaçant le paramètre -Ca par votre propre chemin d'accès à l'autorité de certification) :
    
   ```
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. Ou, après avoir vérifié les entrées SAN dont vous disposez, vous savez que vous avez **plusieurs certificats** qui ne disposent pas de toutes les entrées dont vous avez besoin. Une nouvelle demande de certificat doit être effectuée auprès de votre autorité de certification. Ouvrez votre PowerShell Skype entreprise Server:
    
   - Pour un SAN de service de découverte automatique (en remplaçant le paramètre -Ca par votre propre chemin d'accès à l'autorité de certification) :
    
   ```
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - À présent, si vous avez plusieurs domaines SIP, vous ne pouvez pas utiliser le paramètre AllSipDomain comme dans l’exemple ci-dessus. Vous devrez plutôt utiliser le paramètre DomainName. De plus, lorsque vous utilisez le paramètre DomainName, vous devez définir le nom de domaine complet pour les enregistrements lyncdiscoverinternal et lyncdiscover. En voici des exemples (en remplaçant le paramètre -Ca par votre propre chemin d'accès à l'autorité de certification) :
    
   ```
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

   ```
   Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
   ```

   - Une fois que les nouveaux certificats ont été générés par votre autorité de certification, vous devrez les affecter.
    
### <a name="assign-certificates-using-skype-for-business-server-management-shell"></a>Affecter des certificats à l'aide de Skype Entreprise Server Management Shell

- En fonction de ce que vous avez trouvé dans la section Dois-je obtenir de nouveaux certificats ci-dessus, vous devrez effectuer l'**une ** des mesures suivantes.
    
  - Si vous disposez d'un certificat unique pour tout (les thumbprints sont identiques), vous devez procéder comme suit :
    
  ```
  Set-CsCertificate -Type <certificate(s) from the Use parameter> -Thumbprint <unique identifier>
  ```

  - Si vous disposez de plusieurs certificats (les thumbprints sont tous différents), procédez plutôt comme suit :
    
  ```
  Set-CsCertificate -Type Default -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesInternal -Thumbprint <certificate thumbprint>
  Set-CsCertificate -Type WebServicesExternal -Thumbprint <certificate thumbprint>
  ```

### <a name="viewing-certificates-in-the-microsoft-management-console-mmc"></a>Affichage des certificats dans la console MMC (Microsoft Management Console)

1. Vous avez la possibilité de consulter vos certificats à l'aide du composant logiciel enfichable Certificats pour la console MMC. Saisissez simplement MMC dans la zone de recherche pour les faire apparaître en tant qu'option d'application
    
2. Pour ajouter le composant logiciel enfichable Certificats, cliquez sur **Fichier**, puis sur **Ajouter/Supprimer un composant logiciel enfichable...** (ou utilisez le raccourci clavier **Ctrl+M**). **Certificats** apparaîtra comme option dans le volet de gauche ; sélectionnez-la, puis choisissez **Compte d'ordinateur** dans la fenêtre contextuelle et cliquez sur **Suivant**.
    
3. Vous effectuez probablement cette opération sur l'ordinateur qui héberge les certificats que vous souhaitez consulter, vous pouvez donc laisser la sélection, toujours dans la fenêtre contextuelle, sur **Ordinateur local**. Si vous utilisez une machine distante, changez le bouton radio sur **Autre ordinateur**, puis entrez le nom de domaine complet de cet ordinateur ou utilisez le bouton **Naviguer** pour rechercher cet ordinateur via Active Directory. Après avoir sélectionné l’ordinateur, vous devez cliquer sur **Terminer** lorsque vous êtes prêt, puis sur **OK** pour ajouter le composant logiciel enfichable à la console MMC.
    
4. Développez la section **certificats** dans le volet gauche de la console MMC. Développez également le dossier **Personnel**, puis sélectionnez **Certificats**. Ceci vous permet de visualiser les certificats dans ce magasin.
    
5. Localisez le certificat que vous souhaitez visualiser, cliquez dessus avec le bouton de la souris et sélectionnez **Ouvrir**.
    
    > [!NOTE]
    > Comment savez-vous de quel certificat il s'agit ? Il doit s’agir du certificat unique affecté à tout le contenu de votre batterie de serveurs, ou vous pouvez avoir plusieurs certificats pour différentes choses (par exemple, des services Web internes par défaut, etc.). Plusieurs certificats auront le même thumbprint. 
  
6. Une fois l'affichage **Certificat** défini, sélectionnez **Détails**. Ceci vous permettra de visualiser le nom de l'objet du certificat lorsque vous sélectionnerez **Objet** et le nom de l'objet affecté ainsi que les propriétés associées s'afficheront.
    
7. Vous devrez également vérifier les entrées **Autres noms du sujet **. Les éléments suivants peuvent apparaître :
    
   - Nom du pool pour ce pool ou nom de serveur unique s’il ne s’agit pas d’un pool.
    
   - Nom du serveur auquel le certificat est affecté.
    
   - Enregistrements d’URL simples, généralement meet et dialin.
    
   - Services Web internes et services Web (par exemple, webpool01.contoso.net, webpool01.contoso.com), en fonction des choix effectués dans le générateur de topologie et des sélections de services Web.
    
   - S’il est déjà attribué, le lyncdiscover. \<sipdomain\> et lyncdiscoverinternal. \<enregistrements\> sipdomain.
    
     Vous devrez vérifier les différents certificats dans le cas où plusieurs certificats ont été affectés (consultez la remarque ci-dessus).
    
8. Par conséquent, si vous trouvez lyncdiscover. \<sipdomain\> et lyncdiscoverinternal. \<sipdomain\> les enregistrements que vous avez déjà configurés. Vous pouvez fermer la console MMC.
    
9. S'ils ne sont pas affectés, vous devrez effectuer une nouvelle demande de certificat (telle que décrite ci-dessus) ou les installer une fois la demande effectuée (nous recommandons d'utiliser PowerShell à cet effet).
    
## <a name="configure-the-reverse-proxy"></a>Configurer le proxy inverse
<a name="ConfigRP"> </a>

Les étapes ci-dessous ne doivent pas nécessairement être suivies pas à pas. Dans les versions précédentes de ce produit, nous vous avons par exemple guidé tout au long de la procédure de configuration de Threat Management Gateway (TMG) et si vous ne l'utilisez pas, vous devrez élaborer votre propre procédure selon la version que vous utilisez.
  
TMG n’est plus offert par Microsoft en tant que produit et, si vous le souhaitez, vous pouvez examiner les étapes de la [2013 serveur Lync](https://technet.microsoft.com/en-us/library/hh690011%28v=ocs.15%29.aspx). Toutefois, les informations suivantes sont destinées à être plus utiles, même si vous n’êtes pas en mesure de fournir des étapes de procédures spécifiques pour chaque proxy inverse.
  
Deux points essentiels doivent être pris en compte :
  
- Allez-vous effectuer votre demande de découverte automatique initiale sur HTTPS (ce que nous recommandons) ?
    
  - Si vous avez une règle de publication web, vous devez la modifier.
    
  - Si vous n'avez pas de règle de publication web, vous devez la créer.
    
- Si vous effectuez votre demande de découverte automatique initiale sur HTTPS, vous devrez également créer ou modifier cette règle.
    
> [!NOTE]
> **Important** La valeur du délai d’expiration du proxy est un nombre qui peut varier d’un déploiement au déploiement. Nous vous conseillons de surveiller votre déploiement et de modifier la valeur de la meilleure utilisation pour les clients. Il est possible que vous puissiez définir la valeur sur une valeur inférieure ou égale à 200. Si vous prenez en charge des clients mobiles Lync dans votre environnement, définissez la valeur sur 960 pour autoriser les délais d’expiration de la notification de transmission d’Office 365, qui ont une valeur de délai d’expiration de 900. Il est très probable que vous deviez augmenter la valeur du délai d’expiration pour éviter que le client se déconnecte lorsque la valeur est trop faible, ou si les connexions par le biais du proxy ne se déconnectent pas une fois qu’il a été déconnecté. Le fait de surveiller et de définir ce qui est habituel pour votre environnement est le seul moyen de déterminer le paramètre approprié pour cette valeur.
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a>Modifiez la règle de publication web existante pour votre SAN et URL de découverte automatique externes.

1. Ouvrez votre interface de proxy inverse.
    
2. Vous devez localiser votre règle de publication Web, puis sélectionner l’option modifier (il peut s’agir d’un menu ou d’un onglet, en fonction de votre configuration de proxy inverse).
    
3. Un emplacement doit être utilisé pour indiquer le type de cette règle de publication Web. Vous devez modifier cette règle pour les sites entrants ou les demandes pour les sites. Vous allez **ajouter** une nouvelle entrée.
    
4. Tapez le nom de votre site de découverte automatique (l’exemple utilisé est lyncdiscover.contoso.com), puis cliquez sur **OK** ou sur **Enregistrer**en fonction du format de votre proxy inverse.
    
5. Vous devez avoir un nouveau certificat contenant l'entrée SAN de découverte automatique. Il doit être installé en même temps et configuré pour une utilisation en fonction des paramètres de votre proxy inverse. Assurez-vous de tout sauvegarder une fois la configuration terminée.
    
6. Si votre proxy inverse dispose d’une fonctionnalité de **test** , utilisez-le pour vous assurer que tout fonctionne correctement.
    
7. À présent, il est possible que vous deviez répéter ces étapes si vous disposez d’un directeur ou d’un pool de réalisateur dans votre environnement (cela signifie que vous disposez d’une deuxième règle).
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a>Créer une règle de publication Web pour l’URL de découverte automatique externe

1. Ouvrez votre interface de proxy inverse.
    
2. Vous devez localiser l’emplacement dans l’interface dans laquelle vous créez les règles de publication Web, puis sélectionner l’option **nouveau** ou **créer** (il peut s’agir d’un menu ou d’un onglet, en fonction de votre configuration de proxy inverse). Vous recherchez l'option permettant de créer une nouvelle règle de publication web.
    
3. Vous devrez généralement saisir les informations suivantes :
    
   - **Nom** : le nom de votre règle.
    
   - **Action**de la règle: dans ce cas, il s’agit d’une règle d' **autorisation** , que vous laissez un autre proxy inverse.
    
   - La règle ou l'option de **Publication** que vous choisissez doit être **un seul site web ou équilibrage de charge**.
    
   - Choisissez l'option **SSL** pour l'accès externe.
    
   - Vous devez publier un chemin pour la **publication interne**et entrer le nom de domaine complet (FQDN) pour les services Web externes sur le solde de charge de votre pool frontal (ou le nom de domaine complet (FQDN) du pool de directeurs si vous en avez un), par exemple sfb_ pool01. contoso. local.
    
   - Vous devez taper ** / *** pour le chemin d’accès à publier, mais vous devez également **transférer l’en-tête d’hôte d’origine**.
    
   - Une option vous permettra de sélectionner les informations du **nom public ou externe**. À cet endroit, vous pourrez saisir les informations suivantes :
    
   - **Accepter les demandes**, mais pour le nom de domaine.
    
   - Pour le **Nom**, vous devez saisir **lyncdiscover.** <sipdomain>(il s’agit de l’URL du service de découverte automatique externe). À présent, si vous créez une règle pour l’URL des services Web externes sur le pool frontal, vous devez taper le nom de domaine complet (FQDN) pour les services Web externes dans votre liste frontale (par exemple, lyncwebextpool01.contoso.com).
    
   - Une option **path** sera disponible et vous devrez entrer ** / *** ici.
    
   - Vous devrez sélectionner un **Écouteur SSL** avec votre certificat public à jour.
    
   - **Délégation de l’authentification** doit être définie sur **Aucune délégation**, mais une authentification client directe **doit** être autorisée.
    
   - La règle doit être définie sur **Tous les utilisateurs**.
    
   - Il s'agit de toutes les informations dont vous avez besoin pour créer cette règle et vous permettre de suivre la procédure.
    
4. Vous devez vous assurer que l'**en-tête de l’hôte d’origine** est transmis.
    
5. Les ports du **serveur web** devront également être définis ; procédez de la manière suivante :
    
   - **Rediriger les demandes au port HTTP**, avec le numéro de port **8080**.
    
   - **Rediriger les demandes au port SSL**, avec le numéro de port **4443**.
    
6. Une fois tous les éléments configurés, vous devrez enregistrer et appliquer les paramètres, puis tester la règle.
    
### <a name="create-a-web-publishing-rule-for-port-80-optional"></a>Créer une règle de publication web pour le port 80 (facultatif)

1. Ouvrez votre interface de proxy inverse.
    
2. Vous devez localiser l’emplacement dans l’interface dans laquelle vous créez les règles de publication Web, puis sélectionner l’option **nouveau** ou **créer** (il peut s’agir d’un menu ou d’un onglet, en fonction de votre configuration de proxy inverse). Vous recherchez l'option permettant de créer une nouvelle règle de publication web.
    
3. Vous devrez généralement saisir les informations suivantes :
    
   - **Nom** : le nom de votre règle.
    
   - **Action**de la règle: dans ce cas, il s’agit d’une règle d' **autorisation** , que vous laissez un autre proxy inverse.
    
   - La règle ou l'option de **Publication** que vous choisissez doit être **un seul site web ou équilibrage de charge**.
    
   - Une **connexion non sécurisée est nécessaire pour se connecter au serveur web publié ou à la batterie de serveurs**.
    
   - Vous devez publier un chemin pour la **publication interne**et entrer le nom de domaine complet (FQDN) de l' **adresse VIP** de l’équilibrage de charge de votre pool frontal, par exemple, sfb_pool01. contoso. local.
    
   - Vous devez taper ** / *** pour le chemin d’accès à publier, mais vous devez également **transférer l’en-tête d’hôte d’origine**.
    
   - Une option vous permettra de sélectionner les informations du **nom public ou externe**. À cet endroit, vous pourrez saisir les informations suivantes :
    
   - **Accepter les demandes**, mais pour le nom de domaine.
    
   - Pour le **Nom**, vous devez saisir **lyncdiscover.** <sipdomain>(il s’agit de l’URL du service de découverte automatique externe).
    
   - Une option **path** sera disponible et vous devrez entrer ** / *** ici.
    
   - Vous devez sélectionner un écouteur Web ou autoriser votre proxy inverse à en créer un pour vous.
    
   - **Délégation de l’authentification** doit être définie sur **Aucune délégation**, mais une authentification client directe **ne doit pas** être autorisée.
    
   - La règle doit être définie sur **Tous les utilisateurs**.
    
   - Il s'agit de toutes les informations dont vous avez besoin pour créer cette règle et vous permettre de suivre la procédure.
    
4. Les ports du **serveur web** devront être définis ; procédez de la manière suivante :
    
   - **Rediriger les demandes au port HTTP**, avec le numéro de port **8080**.
    
   - **Rediriger les demandes au port SSL**, avec le numéro de port **4443**.
    
5. Une fois tous les éléments configurés, vous devrez enregistrer et appliquer les paramètres, puis tester la règle.
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a>Configurer la découverte automatique pour la mobilité avec les déploiements hybrides
<a name="ConfigAutoD"> </a>

Les environnements hybrides dans Skype entreprise Server sont des environnements qui combinent un environnement local et Office 365. Lorsque Skype entreprise Server fonctionne dans un environnement hybride, le service de découverte automatique doit être en mesure de rechercher un utilisateur à partir de l’un de ces environnements.
  
Pour permettre aux clients mobiles de découvrir où est localisé un utilisateur, le service de découverte automatique doit être configuré avec une nouvelle URL (uniform resource locator). Les étapes à suivre sont :
  
1. Ouvrez Skype entreprise Server Management Shell.
    
2. Pour obtenir la valeur de l’attribut **ProxyFQDN** pour votre environnement Skype entreprise Server, procédez comme suit:
    
   ```
   Get-CsHostingProvider
   ```

3. Puis, toujours dans la fenêtre de shell, exécutez :
    
   ```
   Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodiscoverservice.svc/root
   ```

    Où [identity] est remplacé par le nom de domaine de l’espace d’adresses SIP partagé.
    
## <a name="test-your-mobility-deployment"></a>Tester votre déploiement de mobilité
<a name="TestMobility"> </a>

Une fois que vous avez déployé le service de mobilité Skype entreprise Server et le service de découverte automatique Skype entreprise Server, vous pouvez exécuter une transaction de test pour vous assurer que votre déploiement fonctionne correctement. Vous pouvez exécuter **Test-CsUcwaConference** afin de tester la capacité de deux utilisateurs à créer et à rejoindre une conférence, ainsi qu'à y communiquer. Il vous faudra deux utilisateurs (réels ou tests) et leurs informations d'identification complètes pour effectuer ce test. Cette commande fonctionne pour les clients Skype entreprise et Lync Server 2013.
  
Pour les clients Lync Server 2010 sur Skype entreprise Server 2015, vous devez exécuter **le test-CsMcxP2PIM** . Vos utilisateurs de Lync Server 2010 doivent toujours être des utilisateurs réels ou des utilisateurs de test prédéfinis et vous aurez besoin de leurs informations d’identification de mot de passe.

> [!NOTE]
> La prise en charge de MCX (service de mobilité) pour les clients mobiles hérités n’est plus disponible dans Skype entreprise Server 2019. Tous les clients mobiles Skype entreprise actuels utilisent déjà UCWA (Unified Communications Web API) pour la prise en charge de la messagerie instantanée, de la présence et des contacts. Les utilisateurs des clients hérités utilisant MCX doivent effectuer une mise à niveau vers un client actuel.
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a>Conférence test pour clients mobiles Skype Entreprise et Lync 2013

1. Ouvrez une session en tant que membre du rôle **CsAdministrator** sur n’importe quel ordinateur sur lequel **Skype entreprise Server Management Shell** et **OCSCore** sont installés.
    
2. Démarrez **Skype entreprise Server Management Shell** (vous pouvez taper le nom dans la zone de recherche ou accédez à **tous les programmes** , puis sélectionnez-le).
    
3. Dans la ligne de commande, saisissez :
    
   ```
   Test-CsUcwaConference -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -OrganizerSipAddress sip:<SIP address of test user 1> -OrganizerCredential <test user 1 credentials> -ParticipantSipAddress sip:<SIP address of test user 2> -ParticipantCredential <test user 2 credentials> -v
   ```

   Il est également possible de définir des informations d’identification dans un script et de les transmettre à l'applet de commande de test. Un exemple est fourni ci-dessous.
    
   ```
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $testuser1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $testuser2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsUcwaConference -TargetFqdn pool01.contoso.com -Authentication Negotiate -OrganizerSipAddress sip:UserName1@contoso.com -OrganizerCredential $testuser1 -ParticipantSipAddress sip:UserName2@contoso.com -ParticipantCredential $testuser2 -v
   ```

### <a name="test-conferencing-for-lync-2010-mobile-clients"></a>Conférence test pour clients mobiles Lync 2010

> [!NOTE]
> La prise en charge de MCX (service de mobilité) pour les clients mobiles hérités n’est plus disponible dans Skype entreprise Server 2019. Tous les clients mobiles Skype entreprise actuels utilisent déjà UCWA (Unified Communications Web API) pour la prise en charge de la messagerie instantanée, de la présence et des contacts. Les utilisateurs des clients hérités utilisant MCX doivent effectuer une mise à niveau vers un client actuel.

1. Ouvrez une session en tant que membre du rôle **CsAdministrator** sur n’importe quel ordinateur sur lequel **Skype entreprise Server Management Shell** et **OCSCore** sont installés.
    
2. Démarrez **Skype entreprise Server Management Shell** (vous pouvez taper le nom dans la zone de recherche ou accédez à **tous les programmes** , puis sélectionnez-le).
    
3. Dans la ligne de commande, saisissez :
    
   ```
   Test-CsMcxP2PIM -TargetFqdn <FQDN of Front End pool> -Authentication <TrustedServer | Negotiate | ClientCertificate | LiveID> -SenderSipAddress sip:<SIP address of test user 1> -SenderCredential <test user 1 credentials> -ReceiverSipAddress sip:<SIP address of test user 2> -ReceiverCredential <test user 2 credentials> -v
   ```

   Il est également possible de définir des informations d’identification dans un script et de les transmettre à l'applet de commande de test. Un exemple est fourni ci-dessous.
    
   ```
   $passwd1 = ConvertTo-SecureString "Password01" -AsPlainText -Force
   $passwd2 = ConvertTo-SecureString "Password02" -AsPlainText -Force
   $tuc1 = New-Object Management.Automation.PSCredential("contoso\UserName1", $passwd1)
   $tuc2 = New-Object Management.Automation.PSCredential("contoso\UserName2", $passwd2)
   Test-CsMcxP2PIM -TargetFqdn pool01.contoso.com -Authentication Negotiate -SenderSipAddress sip:UserName1@contoso.com -SenderCredential $tuc1 -ReceiverSipAddress sip:UserName2@contoso.com -ReceiverCredential $tuc2 -v
   ```

Pour examiner en détail les procédures de commande, vous pouvez consulter [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) et [Test-CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/test-csmcxp2pim?view=skype-ps).
  
## <a name="configure-for-push-notifications"></a>Configurer les notifications push
<a name="ConfigPush"> </a>

Les notifications push, sous forme de badges, d’icônes ou d’alertes, peuvent être envoyées à un appareil mobile même lorsque l'application Skype ou Lync est inactive. Que sont les notifications de transmission? Ce sont des alertes pour des événements, comme des invitations de messagerie instantanée nouvelles ou manquées, ou un message vocal reçu. Le service de mobilité Skype entreprise Server envoie ces notifications au service de notification Poussée dans le Cloud de Skype entreprise Server, qui envoie les notifications au service de notifications de transmission de Microsoft (MSNS) pour les utilisateurs de Windows Phone.
  
Cette fonctionnalité n’est pas modifiée à partir de Lync Server 2013, mais si vous disposez d’un serveur Skype entreprise, vous devez effectuer les opérations suivantes:
  
- Pour un serveur Edge Skype entreprise Server, ajoutez un nouveau fournisseur d’hébergement, Microsoft Skype entreprise Online, puis configurez la Fédération des fournisseurs d’hébergement entre votre organisation et Skype entreprise online.
    
- Activez les notifications push en exécutant l’applet de commande **Set-CsPushNotificationConfiguration**. Par défaut, les notifications push sont désactivées.
    
- Testez votre configuration de fédération et les notifications push.
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a>Configurer Skype Entreprise Edge Server pour les notifications push

1. Ouvrez une session avec un compte membre du rôle **CsAdministrator** sur un ordinateur sur lequel **Skype entreprise Server Management Shell** et **OCSCore** sont installés.
    
2. Démarrez **Skype entreprise Server Management Shell**.
    
3. Ajoutez un fournisseur d’hébergement en ligne Skype entreprise Server.
    
   ```
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   Par exemple :
    
   ```
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > Vous ne pouvez pas avoir plus d’une relation de fédération avec un même fournisseur d’hébergement. Par conséquent, si vous avez déjà configuré un fournisseur d’hébergement ayant une relation de fédération avec sipfed.online.lync.com, vous ne devez pas ajouter d’autre fournisseur d’hébergement, même si l’identité du fournisseur d’hébergement est différente de SkypeOnline. 
  
4. Configurez la Fédération des fournisseurs d’hébergement entre votre organisation et le service de notifications de transmission de Skype entreprise online. Dans la ligne de commande, tapez :
    
   ```
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a>Activer les notifications push

1. Ouvrez une session avec un compte membre du rôle **CsAdministrator** sur un ordinateur sur lequel **Skype entreprise Server Management Shell** et **OCSCore** sont installés.
    
2. Démarrez **Skype entreprise Server Management Shell**.
    
3. Activer les notifications push :
    
   ```
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. Activer la fédération :
     
   ```
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a>Tester la fédération et les notifications push

1. Ouvrez une session avec un compte membre du rôle **CsAdministrator** sur un ordinateur sur lequel **Skype entreprise Server Management Shell** et **OCSCore** sont installés.
    
2. Démarrez **Skype entreprise Server Management Shell**.
    
3. Testez la configuration de la fédération :
    
   ```
   Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
   ```

    Par exemple :
    
   ```
   Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com
   ```

4. Testez vos notifications push
    
   ```
   Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
   ```

    Par exemple :
    
   ```
   Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com
   ```

## <a name="configure-mobility-policy"></a>Configurer la stratégie de mobilité
<a name="ConfigMob"> </a>

Skype entreprise Server vous permet de déterminer qui peut utiliser votre service de mobilité, de passer des appels par le biais de votre travail, de la voix sur IP (VoIP) ou de la vidéo, et si vous avez besoin d’un réseau Wi-Fi ou d’une vidéo. La fonctionnalité d'Appel via le Bureau permet à un utilisateur mobile d'utiliser son numéro de téléphone professionnel, plutôt que son numéro de téléphone mobile, pour passer et recevoir des appels. La personne à l'autre bout de la ligne ne verra pas le numéro de téléphone mobile de cet utilisateur, et cet utilisateur mobile n'aura pas à payer de frais d'appels sortants. Lorsque VoIP et la vidéo sont configurés, les utilisateurs peuvent prendre et effectuer des appels VoIP et vidéo. Les paramètres d'utilisation de la fonctionnalité WiFi permettent de déterminer si l'appareil mobile d'un utilisateur sera requis pour utiliser un réseau WiFi sur un réseau de données cellulaires.
  
Les fonctionnalités de mobilité, d’appel via le bureau et les fonctions VoIP et vidéo sont toutes activées par défaut. Les paramètres pour exiger WiFi pour VoIP et pour la vidéo sont désactivés. Un administrateur a la capacité de modifier ces paramètres, soit de manière globale, soit par site ou par utilisateur.
  
Pour pouvoir utiliser les fonctionnalités de mobilité et l’appel via le bureau, les utilisateurs doivent être:
  
- Activé pour Skype entreprise Server
    
- Activés pour Voix Entreprise
    
- Attribution d’une stratégie de mobilité dont l’option **EnableMobility** est définie sur **true**.
    
Pour pouvoir utiliser la fonctionnalité d'Appel via le Bureau, les utilisateurs doivent également être :
  
- Affectés à une stratégie de voix dont l’option **Activer la sonnerie simultanée de téléphones ** est activée.
    
- Attribution d’une stratégie de mobilité qui utilise la propriété **EnableOutsideVoice** définie sur **true**.
    
> [!NOTE]
> Les utilisateurs non activés pour Voix Entreprise peuvent utiliser leur appareil mobile pour effectuer des appels de Skype à Skype VoIP ou peuvent participer à des conférences via le lien Clic pour participer sur leur appareil mobile, si les options adéquates sont configurées pour la stratégie de voix à laquelle ils sont associés. Vous trouverez plus de détails dans la rubrique Planification. 
  
### <a name="modify-global-mobility-policy"></a>Modifier la stratégie de mobilité globale

1. Ouvrez une session avec un compte membre du rôle **CsAdministrator** sur un ordinateur sur lequel **Skype entreprise Server Management Shell** et **OCSCore** sont installés.
    
2. Démarrez **Skype entreprise Server Management Shell**.
    
3. Désactivez l’accès à la mobilité et aux appels via le mode de fonctionnement global en entrant:
    
   ```
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > Vous pouvez désactiver les appels via le mode de fonctionnement sans désactiver l’accès à la mobilité. En revanche, vous ne pouvez pas désactiver la mobilité sans désactiver la fonction d’appel via le mode de fonctionnement. 
  
    Pour plus d’informations, consultez la rubrique [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).
    
### <a name="modify-mobility-policy-by-site"></a>Modifier la stratégie de mobilité par site

1. Ouvrez une session avec un compte membre du rôle **CsAdministrator** sur un ordinateur sur lequel **Skype entreprise Server Management Shell** et **OCSCore** sont installés.
    
2. Démarrez **Skype entreprise Server Management Shell**.
    
3. Vous pouvez créer une stratégie au niveau du site, désactiver les fonctionnalités VoIP et vidéo et activer l'option Exiger WiFi pour l'audio IP et Exiger WiFi pour la vidéo IP par site.
    
   ```
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    Pour en savoir plus, reportez-vous à [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).
    
### <a name="modify-mobility-policy-by-user"></a>Modifier la stratégie de mobilité par utilisateur

1. Ouvrez une session avec un compte membre du rôle **CsAdministrator** sur un ordinateur sur lequel **Skype entreprise Server Management Shell** et **OCSCore** sont installés.
    
2. Démarrez **Skype entreprise Server Management Shell**.
    
3. Créez des stratégies de mobilité au niveau utilisateur, puis désactivez la mobilité et les appels via votre bureau. Tapez :
    
   ```
   New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
   ```

    Autre exemple avec échantillons de données :
    
   ```
   New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
   Grant-CsMobilityPolicy -Identity MobileUser1@contoso.com -PolicyName tag:disableOutsideVoice
   ```

    > [!NOTE]
    > Vous pouvez désactiver les appels via le mode de fonctionnement sans désactiver l’accès à la mobilité. En revanche, vous ne pouvez pas désactiver la mobilité sans désactiver la fonction d’appel via le mode de fonctionnement. 
  

