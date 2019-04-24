---
title: Déployer et configurer la mobilité pour Skype pour Business Server
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec6197a-3d1e-4b42-9465-564044cdab1a
description: Cet article vous guidera dans les étapes pour configurer un Skype existant pour l’installation de Business Server afin d’utiliser le service de mobilité, qui permet à vos appareils mobiles et être en mesure de tirer parti de Skype pour les fonctionnalités de mobilité Server.
ms.openlocfilehash: c9203bb90f4d4659819a4336c21f08e58785dfde
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32233260"
---
# <a name="deploy-and-configure-mobility-for-skype-for-business-server"></a>Déployer et configurer la mobilité pour Skype pour Business Server  
 
Cet article vous guidera dans les étapes pour configurer un Skype existant pour l’installation de Business Server afin d’utiliser le service de mobilité, qui permet à vos appareils mobiles et être en mesure de tirer parti de Skype pour les fonctionnalités de mobilité Server.
  
Avoir examiné l’article [Plan pour la mobilité pour Skype pour Business Server](../plan-your-deployment/mobility.md) , vous devez être prêt à effectuer les étapes ci-dessous pour déployer la mobilité dans votre Skype pour un environnement de serveur d’entreprise. Voici les étapes à suivre (avec une liste des autorisations incluse dans le tableau) :
  
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
> Prise en charge MCX (Service de mobilité) pour les clients mobiles hérités n’est plus disponible dans Skype pour Business Server 2019. Tous les Skype en cours pour les clients mobiles métiers utilisent déjà Unified Communications Web API (UCWA) pour prendre en charge la messagerie instantanée, présence et les contacts. Les utilisateurs avec les clients hérités MCX doivent mettre à niveau vers un client actuel.
  
## <a name="create-dns-records"></a>Créer des enregistrements DNS
<a name="CreateDNSRec"> </a>

Vous disposez peut-être déjà dans le cadre de votre Skype pour un environnement Business Server, mais vous n’avez pas besoin de créer les enregistrements suivants pour la découverte automatique fonctionner :
  
- un enregistrement DNS interne afin de prendre en charge les utilisateurs mobiles qui se connectent depuis le réseau de votre organisation ;
    
- un enregistrement DNS externe (ou public) afin de prendre en charge les utilisateurs mobiles qui se connectent depuis le réseau de votre organisation.
    
Ces enregistrements sont soit des enregistrements de noms (d'hôte) A, soit des enregistrements CNAME (vous n'avez pas à créer ces deux enregistrements, mais nous décrivons ici toutes les étapes pour les deux types d'enregistrement).
  
### <a name="create-an-internal-dns-cname-record"></a>Créer un enregistrement CNAME DNS interne

1. Ouvrez une session sur un serveur DNS de votre réseau qui est membre du groupe **Administrateurs du domaine** ou du groupe **DnsAdmins**.
    
2. Cliquez sur **Démarrer**, Sélectionnez **Outils d’administration ** (vous devrez peut-être **Rechercher ** l'option si elle n'existe pas dans le menu Démarrer), puis cliquez sur **DNS** pour ouvrir le composant logiciel enfichable d'administration DNS.
    
3. Dans le volet gauche de la fenêtre de console, vous devez accéder au domaine d’accueil à votre Skype pour les serveurs frontaux Business Server et développez **Zones de recherche directes** il.
    
4. Prenez un moment pour vérifiez lequel des enregistrements suivants vous avez :
    
   - N’importe quel A ou AAAA enregistrements d’hôte pour votre serveur frontal (Standard ou Enterprise) ou les pools frontaux.
    
   - N’importe quel hôte (A) ou les enregistrements AAAA pour un directeur ou un directeur (configuration facultative qu'avoir dans votre déploiement) du pool.
    
5. Une fois l'information vérifiée, cliquez avec le bouton droit de la souris sur votre nom de domaine SIP, puis sélectionnez **Nouvel alias (CNAME)** dans le menu.
    
6. Dans la zone **Nom de l’alias**, saisissez le nom d’hôte correspondant à l’URL de service interne de découverte automatique : lyncdiscoverinternal.
    
7. Dans la **nom de domaine complet (nom de domaine complet pour l’hôte cible**, vous devez entrez ou recherchez le nom complet interne des Services Web pour votre Front End pool (ou serveur frontal unique, ou pool directeur ou directeur), identifié à l’étape 4 ci-dessus. Cliquez sur Entrée une fois le nom saisi.
    
8. Vous devez créer un nouvel enregistrement CNAME Autodiscover dans la zone de recherche directe pour chaque domaine SIP pris en charge dans votre Skype pour un environnement de serveur d’entreprise.
    
### <a name="create-an-external-dns-cname-record"></a>Créer un enregistrement CNAME DNS externe

1. Ces étapes sont génériques, car nous ne pouvons pas déterminer quel fournisseur DNS public vous utilisez, mais elles pourront toujours vous être utiles. Connectez-vous à votre fournisseur DNS public avec un compte qui vous permettra de créer ici de nouveaux enregistrements DNS.
    
2. À ce stade, un domaine SIP doit déjà exister il pour Skype pour Business Server. Développez la **zone de recherche directe** pour ce domaine SIP, ou procédez à son ouverture.
    
3. Prenez un moment pour vérifiez lequel des enregistrements suivants vous avez :
    
   - N’importe quel A ou AAAA enregistrements d’hôte pour votre serveur frontal (Standard ou Enterprise) ou les pools frontaux.
    
   - N’importe quel hôte (A) ou les enregistrements AAAA pour un directeur ou un directeur (configuration facultative qu'avoir dans votre déploiement) du pool.
    
4. Une fois que vous avez vérifié l'information, vous devriez pouvoir sélectionner une option pour créer un **Nouvel alias (CNAME)**.
    
5. Vous devriez maintenant pouvoir saisir un **Nom d'alias**. Saisissez ensuite lyncdiscover en tant qu'URL de service interne de découverte automatique.
    
6. Suivant doit être une zone d’entrer dans un **nom de domaine complet pour l’hôte de destination**, il doit être le nom de domaine complet pour votre Front End pool (ou serveur frontal unique, ou pool directeur ou directeur), identifié à l’étape 3.
    
7. Vous devrez peut-être enregistrer ici, ou si vous avez besoin créer des enregistrements CNAME supplémentaires dans la zone de recherche directe de chaque domaine SIP dans votre Skype pour un environnement Business Server, vous le faire, mais une fois que vous êtes prêt, enregistrez votre travail.
    
### <a name="create-an-internal-dns-a-record"></a>Créer un enregistrement A DNS interne

1. Ouvrez une session sur un serveur DNS de votre réseau qui est membre du groupe **Administrateurs du domaine** ou du groupe **DnsAdmins**.
    
2. Cliquez sur **Démarrer**, Sélectionnez **Outils d’administration ** (vous devrez peut-être **Rechercher ** l'option si elle n'existe pas dans le menu Démarrer), puis cliquez sur **DNS** pour ouvrir le composant logiciel enfichable d'administration DNS.
    
3. Dans le volet gauche de la fenêtre de console, vous devez accéder au domaine d’accueil à votre Skype pour les serveurs frontaux Business Server et développez **Zones de recherche directes** il.
    
4. Prenez un moment pour vérifiez lequel des enregistrements suivants vous avez :
    
   - N’importe quel A ou AAAA enregistrements d’hôte pour votre serveur frontal (Standard ou Enterprise) ou les pools frontaux.
    
   - N’importe quel hôte (A) ou les enregistrements AAAA pour un directeur ou un directeur (configuration facultative qu'avoir dans votre déploiement) du pool.
    
5. Une fois l'information vérifiée, cliquez avec le bouton droit de la souris sur votre nom de domaine SIP, puis sélectionnez **Nouvel hôte (A ou AAAA)** dans le menu.
    
6. Dans la zone **Nom**, saisissez le nom d’hôte correspondant à l’URL de service interne de découverte automatique : lyncdiscoverinternal.
    
7. Dans la zone de texte **Adresse IP** , tapez l’adresse IP des Services Web interne pour votre Front End pool (ou serveur frontal unique, ou pool directeur ou directeur), identifié à l’étape 4 ci-dessus.
    
8. Une fois terminé, cliquez sur **Ajouter un hôte**, puis cliquez sur **OK**.
    
9. Vous devez créer des enregistrements Autodiscover A ou AAAA de la zone de recherche directe pour chaque domaine SIP pris en charge dans votre Skype pour un environnement Business Server. Pour ce faire, répétez les étapes 6 à 8 autant de fois que nécessaire.
    
10. Une fois l'opération terminée, cliquez sur **Terminé**.
    
### <a name="create-an-external-dns-a-record"></a>Créer un enregistrement A DNS externe

1. Ces étapes sont génériques, car nous ne pouvons pas déterminer quel fournisseur DNS public vous utilisez, mais elles pourront toujours vous être utiles. Connectez-vous à votre fournisseur DNS public avec un compte qui vous permettra de créer ici de nouveaux enregistrements DNS.
    
2. À ce stade, un domaine SIP doit déjà exister il pour Skype pour Business Server. Développez la **zone de recherche directe** pour ce domaine SIP, ou procédez à son ouverture.
    
3. Prenez un moment pour vérifiez lequel des enregistrements suivants vous avez :
    
   - N’importe quel A ou AAAA enregistrements d’hôte pour votre serveur frontal (Standard ou Enterprise) ou les pools frontaux.
    
   - N’importe quel hôte (A) ou les enregistrements AAAA pour un directeur ou un directeur (configuration facultative qu'avoir dans votre déploiement) du pool.
    
4. Une fois que vous avez vérifié l'information, vous devriez être capable de sélectionner une option pour créer un **Nouvel hôte A ou AAAA)**.
    
5. Vous devriez maintenant pouvoir saisir un **Nom**. Saisissez ensuite lyncdiscover en tant qu'URL de service interne de découverte automatique.
    
6. Ensuite, il doit y avoir une zone d’entrer dans une **Adresse IP**, cela doit être l’adresse IP de votre Front End pool (ou serveur frontal unique, ou pool directeur ou directeur), identifié à l’étape 3 ci-dessus.
    
7. Vous devrez peut-être enregistrer ici, ou si vous devez créer d’autres A ou AAAA des enregistrements dans la zone de recherche directe de chaque domaine SIP pour votre Skype pour un environnement Business Server, vous devez le faire, mais lorsque vous êtes prêt, enregistrez votre travail.
    
## <a name="modify-certificates"></a>Modifier les certificats
<a name="ModCerts"> </a>

Si vous avez des questions sur la planification autour de certificats, nous avons qui documentée dans notre article de [planification pour la mobilité pour Skype pour Business Server](../plan-your-deployment/mobility.md) . Une fois que vous avez vérifié que, nous allons vous aider aux éléments suivants :
  
- Dois-je obtenir de nouveaux certificats ?
    
- Demande de nouveaux certificats auprès de votre autorité de certification (CA).
    
- Mise à jour sur site de certificats avec les remplacements à l'aide de PowerShell.
    
- Vérification des certificats à l’aide du composant logiciel enfichable Certificats dans Microsoft Management Console (MMC).
    
### <a name="do-i-need-new-certificates"></a>Dois-je obtenir de nouveaux certificats ?

1. Vous devez d'abord vérifier quels certificats sont en place et s'ils disposent ou non des entrées dont vous avez besoin. Pour cela, vous devez connecter votre Skype pour Business Server avec un compte qui est un administrateur local. Ce compte doit également disposer des autorisations d'accès à l'autorité de certification (CA) émettrice pour effectuer certaines de ces étapes.
    
2. Ouvrez le Skype pour Business Server Management Shell (vous pouvez utiliser recherche trouver si vous ne l’avez pas épinglés à la barre de menu ou de la tâche Démarrer).
    
3. Vous devrez absolument savoir quels certificats ont été affectés avant de pouvoir ajouter un certificat mis à jour. À partir de la ligne de commande, saisissez ce qui suit :
    
   ```
   Get-CsCertificate
   ```

4. Les informations fournies à partir de l'étape 3 vous seront spécifiques. Vous devez les vérifier afin de déterminer si vous disposez d'un certificat unique ayant été affecté à plusieurs éléments, ou si vous disposez d'un autre certificat affecté pour les différents composants qui en ont besoin. Le paramètre **Utiliser** vous permettra de savoir de quelle manière un certificat est utilisé et le paramètre **Thumbprint** vous permettra de savoir s'il s'agit du même certificat ou de plusieurs certificats.
    
5. Si vous disposez des entrées SAN recommandées dans votre section Planification, vous n'avez rien à faire. Sinon, vous devrez demander un nouveau certificat ou plusieurs certificats (en fonction de votre configuration) auprès de votre autorité de certification.
    
### <a name="request-a-new-certificate-or-certificates-from-your-certificate-authority-ca"></a>Demander un nouveau certificat ou de nouveaux certificats auprès de votre autorité de certification (CA)

1. Après avoir vérifié les entrées SAN dont vous disposez, vous savez que vous avez un **certificat unique** (la vérification ayant été effectuée en suivant la procédure décrite précédemment) et vous savez que vous ne disposez pas de toutes les entrées dont vous avez besoin. Une nouvelle demande de certificat doit être effectuée auprès de votre autorité de certification. Ouvrez votre Skype pour Business Server PowerShell :
    
   - Pour un SAN de service de découverte automatique (en remplaçant le paramètre -Ca par votre propre chemin d'accès à l'autorité de certification) :
    
   ```
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - Maintenant, si vous avez plusieurs domaines SIP, vous ne pouvez pas utiliser le paramètre AllSipDomain comme dans l’exemple ci-dessus. Vous devrez plutôt utiliser le paramètre DomainName. De plus, lorsque vous utilisez le paramètre DomainName, vous devez définir le nom de domaine complet pour les enregistrements lyncdiscoverinternal et lyncdiscover. En voici un exemple (en remplaçant le paramètre -Ca par votre propre chemin d'accès à l'autorité de certification) :
    
   ```
   Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
   ```

2. Ou, après avoir vérifié les entrées SAN dont vous disposez, vous savez que vous avez **plusieurs certificats** qui ne disposent pas de toutes les entrées dont vous avez besoin. Une nouvelle demande de certificat doit être effectuée auprès de votre autorité de certification. Ouvrez votre Skype pour Business Server PowerShell :
    
   - Pour un SAN de service de découverte automatique (en remplaçant le paramètre -Ca par votre propre chemin d'accès à l'autorité de certification) :
    
   ```
   Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
   ```

   - Maintenant, si vous avez plusieurs domaines SIP, vous ne pouvez pas utiliser le paramètre AllSipDomain comme dans l’exemple ci-dessus. Vous devrez plutôt utiliser le paramètre DomainName. De plus, lorsque vous utilisez le paramètre DomainName, vous devez définir le nom de domaine complet pour les enregistrements lyncdiscoverinternal et lyncdiscover. En voici des exemples (en remplaçant le paramètre -Ca par votre propre chemin d'accès à l'autorité de certification) :
    
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
    
3. Vous effectuez probablement cette opération sur l'ordinateur qui héberge les certificats que vous souhaitez consulter, vous pouvez donc laisser la sélection, toujours dans la fenêtre contextuelle, sur **Ordinateur local**. Si vous utilisez une machine distante, changez le bouton radio sur **Autre ordinateur**, puis entrez le nom de domaine complet de cet ordinateur ou utilisez le bouton **Naviguer** pour rechercher cet ordinateur via Active Directory. Après avoir sélectionné l’ordinateur, vous devez cliquez sur **Terminer** lorsque vous êtes prêt, puis sur **OK** pour ajouter le composant logiciel enfichable à la console MMC.
    
4. Développez la section **certificats** dans le volet gauche de la console MMC. Développez également le dossier **Personnel**, puis sélectionnez **Certificats**. Ceci vous permet de visualiser les certificats dans ce magasin.
    
5. Localisez le certificat que vous souhaitez visualiser, cliquez dessus avec le bouton de la souris et sélectionnez **Ouvrir**.
    
    > [!NOTE]
    > Comment savez-vous de quel certificat il s'agit ? Il doit être soit le certificat unique assigné à tous les éléments de votre batterie de serveurs, ou avoir plusieurs certificats différents éléments, tels que la valeur par défaut, les Services Web internes, etc., auquel cas vous devrez peut-être consulter plusieurs certificats. Plusieurs certificats auront le même thumbprint. 
  
6. Une fois l'affichage **Certificat** défini, sélectionnez **Détails**. Ceci vous permettra de visualiser le nom de l'objet du certificat lorsque vous sélectionnerez **Objet** et le nom de l'objet affecté ainsi que les propriétés associées s'afficheront.
    
7. Vous devrez également vérifier les entrées **Autres noms du sujet **. Les éléments suivants peuvent apparaître :
    
   - Le nom du pool pour ce pool ou le nom de serveur unique, si ce n’est pas un pool.
    
   - Nom du serveur auquel le certificat est affecté.
    
   - Enregistrements d’URL simples, généralement meet et dialin.
    
   - Services Web internes et Services Web externes noms (par exemple, webpool01.contoso.net, webpool01.contoso.com), en fonction des choix effectués dans le Générateur de topologie et substituées sélections de Services Web.
    
   - Si déjà affecté, le lyncdiscover. \<sipdomain\> et lyncdiscoverinternal. \<sipdomain\> enregistrements.
    
     Vous devrez vérifier les différents certificats dans le cas où plusieurs certificats ont été affectés (consultez la remarque ci-dessus).
    
8. Par conséquent, si vous recherchez lyncdiscover. \<sipdomain\> et lyncdiscoverinternal. \<sipdomain\> enregistrements, vous obtenez ce configuré déjà. Vous pouvez fermer la console MMC.
    
9. S'ils ne sont pas affectés, vous devrez effectuer une nouvelle demande de certificat (telle que décrite ci-dessus) ou les installer une fois la demande effectuée (nous recommandons d'utiliser PowerShell à cet effet).
    
## <a name="configure-the-reverse-proxy"></a>Configurer le proxy inverse
<a name="ConfigRP"> </a>

Les étapes ci-dessous ne doivent pas nécessairement être suivies pas à pas. Dans les versions précédentes de ce produit, nous vous avons par exemple guidé tout au long de la procédure de configuration de Threat Management Gateway (TMG) et si vous ne l'utilisez pas, vous devrez élaborer votre propre procédure selon la version que vous utilisez.
  
TMG n’est plus offert par Microsoft en tant que produit, et si vous avez besoin de configurer, vous pouvez consulter les [étapes de Lync Server 2013](https://technet.microsoft.com/en-us/library/hh690011%28v=ocs.15%29.aspx). Mais les informations suivantes de destiné à être plus utile, même s’il n’existe aucun moyen que nous pouvons fournir une procédure spécifique pour chaque proxy inverse.
  
Deux points essentiels doivent être pris en compte :
  
- Allez-vous effectuer votre demande de découverte automatique initiale sur HTTPS (ce que nous recommandons) ?
    
  - Si vous avez une règle de publication web, vous devez la modifier.
    
  - Si vous n'avez pas de règle de publication web, vous devez la créer.
    
- Si vous effectuez votre demande de découverte automatique initiale sur HTTPS, vous devrez également créer ou modifier cette règle.
    
> [!NOTE]
> **Important** Une valeur de délai d’expiration du Proxy est un nombre qui varie d’un déploiement à. Vous devez analyser votre déploiement et modifiez la valeur pour optimiser les performances pour les clients. Vous ne pourrez pas définir la valeur aussi faible que 200. Si vous prenez en charge les clients mobiles Lync dans votre environnement, vous devez définir la valeur à 960 permettant de délais d’attente de notification push d’Office 365, qui ont une valeur de délai d’expiration de 900. Il est très probable que vous devrez augmenter la valeur de délai d’expiration pour éviter le client se déconnecte lors de la valeur est trop faible ou diminuer le nombre si les connexions via le proxy ne vous déconnectez pas, mais désactivez long une fois que le client est déconnecté. Analyse et comparaison habituel pour votre environnement est la seule façon de déterminer le paramètre approprié pour cette valeur.
  
### <a name="modify-the-existing-web-publishing-rule-for-your-external-autodiscover-san-and-url"></a>Modifiez la règle de publication web existante pour votre SAN et URL de découverte automatique externes.

1. Ouvrez votre interface de proxy inverse.
    
2. Vous devez localiser votre règle de publication web, puis choisissez l’option Modifier (il peut se trouver sur un menu ou un onglet, selon votre configuration de proxy inverse).
    
3. Il doit être indiquant que cette règle de publication web qui est appliquée à une zone. Vous devez modifier cette règle pour les sites entrants ou les demandes pour les sites. Vous allez **ajouter** une nouvelle entrée.
    
4. Tapez le nom de votre site de découverte automatique (l’exemple, nous allons utiliser est lyncdiscover.contoso.com), puis cliquez sur **OK** ou sur **Enregistrer**, selon le format de votre serveur proxy inverse.
    
5. Vous devez avoir un nouveau certificat contenant l'entrée SAN de découverte automatique. Qui doit être installé et configurés pour être utilisés en fonction des paramètres de votre serveur proxy inverse. Assurez-vous de tout sauvegarder une fois la configuration terminée.
    
6. Si votre serveur proxy inverse a une fonctionnalité de **Test** , puis vérifiez utilisation, afin de tout fonctionne correctement.
    
7. Maintenant, vous devrez peut-être Répétez ces étapes si vous disposez d’un directeur ou un directeur pool dans votre environnement (cela signifie que vous avez une deuxième règle).
    
### <a name="create-a-web-publishing-rule-for-the-external-autodiscover-url"></a>Créer une règle de publication web pour l’URL de découverte automatique externe

1. Ouvrez votre interface de proxy inverse.
    
2. Vous devez localiser où dans l’interface que vous créez vos règles de publication web, choisissez l’option **Nouveau** ou **créer** (il peut se trouver sur un menu ou un onglet, selon votre configuration de proxy inverse). Vous recherchez l'option permettant de créer une nouvelle règle de publication web.
    
3. Vous devrez généralement saisir les informations suivantes :
    
   - **Nom** : le nom de votre règle.
    
   - **Action de la règle**: dans ce cas, il est une règle **d’autorisation** , vous désinscrire quelque chose transitant par votre serveur proxy inverse.
    
   - La règle ou l'option de **Publication** que vous choisissez doit être **un seul site web ou équilibrage de charge**.
    
   - Choisissez l'option **SSL** pour l'accès externe.
    
   - Vous aurez besoin publier un chemin d’accès pour la **Publication interne**, puis entrez le nom de domaine complet pour les Services Web externes d’équilibrage de charge de votre pool frontal (ou nom de domaine complet de l’équilibrage de charge du pool directeur si vous en avez un), un exemple serait sfb_ pool01.contoso.local.
    
   - Vous devez taper ** / *** comme le chemin d’accès à publier, mais vous devez également **transmettre l’en-tête d’hôte d’origine**.
    
   - Une option vous permettra de sélectionner les informations du **nom public ou externe**. À cet endroit, vous pourrez saisir les informations suivantes :
    
   - **Accepter les demandes**, mais pour le nom de domaine.
    
   - Pour le **Nom**, vous devez saisir **lyncdiscover.** <sipdomain>(c’est l’URL externe du Service de découverte automatique). Maintenant, si vous créez une règle pour l’URL des Services Web externes sur le pool frontal, vous devez taper le nom de domaine complet pour les Services Web externes sur votre pool frontal (par exemple, lyncwebextpool01.contoso.com).
    
   - Il y aura une option de **chemin d’accès** , et vous devrez saisir ** / *** ici.
    
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
    
2. Vous devez localiser où dans l’interface que vous créez vos règles de publication web, choisissez l’option **Nouveau** ou **créer** (il peut se trouver sur un menu ou un onglet, selon votre configuration de proxy inverse). Vous recherchez l'option permettant de créer une nouvelle règle de publication web.
    
3. Vous devrez généralement saisir les informations suivantes :
    
   - **Nom** : le nom de votre règle.
    
   - **Action de la règle**: dans ce cas, il est une règle **d’autorisation** , vous désinscrire quelque chose transitant par votre serveur proxy inverse.
    
   - La règle ou l'option de **Publication** que vous choisissez doit être **un seul site web ou équilibrage de charge**.
    
   - Une **connexion non sécurisée est nécessaire pour se connecter au serveur web publié ou à la batterie de serveurs**.
    
   - Vous aurez besoin publier un chemin d’accès pour la **Publication interne**, puis entrez le nom de domaine complet de l' **adresse IP virtuelle** du programme d’équilibrage de charge de votre pool frontal, un exemple serait sfb_pool01.contoso.local.
    
   - Vous devez taper ** / *** comme le chemin d’accès à publier, mais vous devez également **transmettre l’en-tête d’hôte d’origine**.
    
   - Une option vous permettra de sélectionner les informations du **nom public ou externe**. À cet endroit, vous pourrez saisir les informations suivantes :
    
   - **Accepter les demandes**, mais pour le nom de domaine.
    
   - Pour le **Nom**, vous devez saisir **lyncdiscover.** <sipdomain>(c’est l’URL externe du Service de découverte automatique).
    
   - Il y aura une option de **chemin d’accès** , et vous devrez saisir ** / *** ici.
    
   - Vous devez sélectionner un port d’écoute web, ou autoriser votre proxy inverse créer une pour vous.
    
   - **Délégation de l’authentification** doit être définie sur **Aucune délégation**, mais une authentification client directe **ne doit pas** être autorisée.
    
   - La règle doit être définie sur **Tous les utilisateurs**.
    
   - Il s'agit de toutes les informations dont vous avez besoin pour créer cette règle et vous permettre de suivre la procédure.
    
4. Les ports du **serveur web** devront être définis ; procédez de la manière suivante :
    
   - **Rediriger les demandes au port HTTP**, avec le numéro de port **8080**.
    
   - **Rediriger les demandes au port SSL**, avec le numéro de port **4443**.
    
5. Une fois tous les éléments configurés, vous devrez enregistrer et appliquer les paramètres, puis tester la règle.
    
## <a name="configure-autodiscover-for-mobility-with-hybrid-deployments"></a>Configurer la découverte automatique pour la mobilité avec les déploiements hybrides
<a name="ConfigAutoD"> </a>

Environnements hybrides dans Skype pour Business Server sont des environnements qui associent un locaux et environnement O365. Lorsque vous avez Skype pour fonctionner dans un environnement hybride de Business Server, le service de découverte automatique doit être en mesure de localiser un utilisateur d’une de ces environnements.
  
Pour permettre aux clients mobiles de découvrir où est localisé un utilisateur, le service de découverte automatique doit être configuré avec une nouvelle URL (uniform resource locator). Les étapes à suivre sont :
  
1. Ouvrez Skype pour Business Server Management Shell.
    
2. Exécutez la procédure suivante pour obtenir la valeur de l’attribut **ProxyFQDN** pour votre Skype pour un environnement Business Server :
    
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

Une fois que vous avez déployé Skype pour Service de mobilité Business Server et Skype pour le Service de découverte automatique Business Server, vous souhaiterez exécuter une transaction de test, vérifiez que travail de votre déploiement droite. Vous pouvez exécuter **Test-CsUcwaConference** afin de tester la capacité de deux utilisateurs à créer et à rejoindre une conférence, ainsi qu'à y communiquer. Il vous faudra deux utilisateurs (réels ou tests) et leurs informations d'identification complètes pour effectuer ce test. Cette commande fonctionne pour les deux Skype pour les clients d’entreprise, ainsi que les clients Lync Server 2013.
  
Pour les clients Lync Server 2010 sur Skype pour Business Server 2015, vous devrez exécuter **Test-CsMcxP2PIM** pour tester. Vos utilisateurs de Lync Server 2010 devra toujours être réels utilisateurs ou aux utilisateurs de test prédéfinies, et vous aurez besoin de leurs informations d’identification de mot de passe.

> [!NOTE]
> Prise en charge MCX (Service de mobilité) pour les clients mobiles hérités n’est plus disponible dans Skype pour Business Server 2019. Tous les Skype en cours pour les clients mobiles métiers utilisent déjà Unified Communications Web API (UCWA) pour prendre en charge la messagerie instantanée, présence et les contacts. Les utilisateurs avec les clients hérités MCX doivent mettre à niveau vers un client actuel.
  
### <a name="test-conferencing-for-skype-for-business-and-lync-2013-mobile-clients"></a>Conférence test pour clients mobiles Skype Entreprise et Lync 2013

1. Ouvrez une session en tant que membre du rôle **CsAdministrator** sur n’importe quel ordinateur où **Skype pour Business Server Management Shell** et **Ocscore** sont installés.
    
2. Démarrez **Skype pour Business Server Management Shell** (vous pourrez taper le nom de la recherche ou accédez à **Tous les programmes** et choisissez).
    
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
> Prise en charge MCX (Service de mobilité) pour les clients mobiles hérités n’est plus disponible dans Skype pour Business Server 2019. Tous les Skype en cours pour les clients mobiles métiers utilisent déjà Unified Communications Web API (UCWA) pour prendre en charge la messagerie instantanée, présence et les contacts. Les utilisateurs avec les clients hérités MCX doivent mettre à niveau vers un client actuel.

1. Ouvrez une session en tant que membre du rôle **CsAdministrator** sur n’importe quel ordinateur où **Skype pour Business Server Management Shell** et **Ocscore** sont installés.
    
2. Démarrez **Skype pour Business Server Management Shell** (vous pourrez taper le nom de la recherche ou accédez à **Tous les programmes** et choisissez).
    
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

Les notifications push, sous forme de badges, d’icônes ou d’alertes, peuvent être envoyées à un appareil mobile même lorsque l'application Skype ou Lync est inactive. Mais quels sont les notifications push ? Ce sont des alertes pour des événements, comme des invitations de messagerie instantanée nouvelles ou manquées, ou un message vocal reçu. Le Skype pour le service de mobilité Server envoie ces notifications vers le nuage Skype pour Business Server Service de notifications Push, qui envoie ensuite les notifications à Microsoft Push Notification Service (MSNS) pour les utilisateurs de Windows Phone.
  
Cette fonctionnalité est inchangée de Lync Server 2013, mais si vous avez un Skype pour Business Server, vous souhaiterez effectuer les opérations suivantes :
  
- Pour un Skype pour Business Server Edge Server, ajoutez un nouveau fournisseur d’hébergement, Microsoft Skype pour Business Online et puis configurer la fédération d’hébergement fournisseur entre votre organisation et de Skype pour Business Online.
    
- Activez les notifications push en exécutant l’applet de commande **Set-CsPushNotificationConfiguration**. Par défaut, les notifications push sont désactivées.
    
- Testez votre configuration de fédération et les notifications push.
    
### <a name="configure-your-skype-for-business-edge-server-for-push-notifications"></a>Configurer Skype Entreprise Edge Server pour les notifications push

1. Ouvrez une session, avec un compte qui est membre du rôle **CsAdministrator** , sur un ordinateur où **Skype pour Business Server Management Shell** et **Ocscore** sont installés.
    
2. Démarrez le **Skype pour Business Server Management Shell**.
    
3. Ajoutez un Skype pour le fournisseur d’hébergement en ligne Business Server.
    
   ```
   New-CsHostingProvider -Identity <unique identifier for hosting provider> -Enabled $True -ProxyFQDN <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
   ```

   Par exemple :
    
   ```
   New-CsHostingProvider -Identity "SkypeOnline" -Enabled $True -ProxyFQDN "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
   ```

    > [!NOTE]
    > Vous ne pouvez pas avoir plus d’une relation de fédération avec un même fournisseur d’hébergement. Par conséquent, si vous avez déjà configuré un fournisseur d’hébergement ayant une relation de fédération avec sipfed.online.lync.com, vous ne devez pas ajouter d’autre fournisseur d’hébergement, même si l’identité du fournisseur d’hébergement est différente de SkypeOnline. 
  
4. Configurer la fédération de fournisseur d’hébergement entre votre organisation et le Service de Notification Push à Skype pour Business Online. Dans la ligne de commande, tapez :
    
   ```
    New-CsAllowedDomain -Identity "push.lync.com"
   ```

### <a name="enable-push-notifications"></a>Activer les notifications push

1. Ouvrez une session, avec un compte qui est membre du rôle **CsAdministrator** , sur un ordinateur où **Skype pour Business Server Management Shell** et **Ocscore** sont installés.
    
2. Démarrez le **Skype pour Business Server Management Shell**.
    
3. Activer les notifications push :
    
   ```
   Set-CsPushNotificationConfiguration -EnableMicrosoftPushNotificationService $True
   ```

4. Activer la fédération :
     
   ```
   Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
   ```

### <a name="test-federation-and-push-notifications"></a>Tester la fédération et les notifications push

1. Ouvrez une session, avec un compte qui est membre du rôle **CsAdministrator** , sur un ordinateur où **Skype pour Business Server Management Shell** et **Ocscore** sont installés.
    
2. Démarrez le **Skype pour Business Server Management Shell**.
    
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

Vous avez la possibilité avec Skype pour Business Server afin de déterminer qui peut utiliser votre service de mobilité, appel via le bureau, voix sur IP (VoIP), ou la vidéo, ainsi que si Wi-Fi sera nécessaire pour VoIP ou vidéo. La fonctionnalité d'Appel via le Bureau permet à un utilisateur mobile d'utiliser son numéro de téléphone professionnel, plutôt que son numéro de téléphone mobile, pour passer et recevoir des appels. La personne à l'autre bout de la ligne ne verra pas le numéro de téléphone mobile de cet utilisateur, et cet utilisateur mobile n'aura pas à payer de frais d'appels sortants. Lorsque VoIP et la vidéo sont configurés, les utilisateurs peuvent prendre et effectuer des appels VoIP et vidéo. Les paramètres d'utilisation de la fonctionnalité WiFi permettent de déterminer si l'appareil mobile d'un utilisateur sera requis pour utiliser un réseau WiFi sur un réseau de données cellulaires.
  
Mobilité, appel via le bureau et la VoIP et les fonctionnalités vidéo sont toutes activées par défaut. Les paramètres pour exiger WiFi pour VoIP et pour la vidéo sont désactivés. Un administrateur a la capacité de modifier ces paramètres, soit de manière globale, soit par site ou par utilisateur.
  
Pour être en mesure d’utiliser les fonctionnalités de mobilité et d’appel via le bureau, les utilisateurs doivent être :
  
- Activé pour Skype pour Business Server
    
- Activés pour Voix Entreprise
    
- Attribué une stratégie de mobilité dont l’option **EnableMobility** a la valeur **True**.
    
Pour pouvoir utiliser la fonctionnalité d'Appel via le Bureau, les utilisateurs doivent également être :
  
- Affectés à une stratégie de voix dont l’option **Activer la sonnerie simultanée de téléphones ** est activée.
    
- Attribué une stratégie de mobilité dont l' **EnableOutsideVoice** a la valeur **True**.
    
> [!NOTE]
> Les utilisateurs non activés pour Voix Entreprise peuvent utiliser leur appareil mobile pour effectuer des appels de Skype à Skype VoIP ou peuvent participer à des conférences via le lien Clic pour participer sur leur appareil mobile, si les options adéquates sont configurées pour la stratégie de voix à laquelle ils sont associés. Vous trouverez plus de détails dans la rubrique Planification. 
  
### <a name="modify-global-mobility-policy"></a>Modifier la stratégie de mobilité globale

1. Ouvrez une session, avec un compte qui est membre du rôle **CsAdministrator** , sur un ordinateur où **Skype pour Business Server Management Shell** et **Ocscore** sont installés.
    
2. Démarrez le **Skype pour Business Server Management Shell**.
    
3. Désactiver l’accès à la mobilité et l’appel via le bureau global en tapant :
    
   ```
   Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
   ```

    > [!NOTE]
    > Vous pouvez désactiver l’appel via le bureau sans désactiver l’accès à la mobilité. Mais vous ne pouvez pas désactiver la mobilité sans également désactiver appel via le bureau. 
  
    Pour plus d’informations, consultez la rubrique [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/set-csmobilitypolicy?view=skype-ps).
    
### <a name="modify-mobility-policy-by-site"></a>Modifier la stratégie de mobilité par site

1. Ouvrez une session, avec un compte qui est membre du rôle **CsAdministrator** , sur un ordinateur où **Skype pour Business Server Management Shell** et **Ocscore** sont installés.
    
2. Démarrez le **Skype pour Business Server Management Shell**.
    
3. Vous pouvez créer une stratégie au niveau du site, désactiver les fonctionnalités VoIP et vidéo et activer l'option Exiger WiFi pour l'audio IP et Exiger WiFi pour la vidéo IP par site.
    
   ```
   New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $false -RequireWiFiForIPAudio $True -RequireWiFiforIPVideo $True
   ```

    Pour en savoir plus, reportez-vous à [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps).
    
### <a name="modify-mobility-policy-by-user"></a>Modifier la stratégie de mobilité par utilisateur

1. Ouvrez une session, avec un compte qui est membre du rôle **CsAdministrator** , sur un ordinateur où **Skype pour Business Server Management Shell** et **Ocscore** sont installés.
    
2. Démarrez le **Skype pour Business Server Management Shell**.
    
3. Créer des stratégies de mobilité au niveau utilisateur et de désactiver la mobilité et l’appel via le bureau par utilisateur. Tapez :
    
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
    > Vous pouvez désactiver l’appel via le bureau sans désactiver l’accès à la mobilité. Mais vous ne pouvez pas désactiver la mobilité sans également désactiver appel via le bureau. 
  

