---
title: 'Lync Server 2013 : Configuration des règles de publication web pour un pool interne unique'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure web publishing rules for a single internal pool
ms:assetid: 86ff4b2a-1ba9-46a2-a175-8b19e00a49dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429712(v=OCS.15)
ms:contentKeyID: 48184725
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ffe61072df14e28c20c45eb72302905986c6357
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838335"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-web-publishing-rules-for-a-single-internal-pool-in-lync-server-2013"></a>Configuration des règles de publication web pour un pool interne unique dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2014-07-07_

Microsoft Forefront Threat Management Gateway 2010 et le routage de requête d’application Internet Information Server (IIS ARR) utilise des règles de publication Web pour publier les ressources internes, telles qu’une URL de réunion, pour les utilisateurs sur Internet.

Outre les URL des services Web pour les répertoires virtuels, vous devez également créer des règles de publication pour les URL simples, l’URL LyncDiscover et le serveur Office Web Apps. Pour chaque URL simple, vous devez créer une règle individuelle sur le proxy inverse qui pointe vers cette URL simple.

Si vous déployez la mobilité et utilisez la découverte automatique, vous devez créer une règle de publication pour l’URL du service de découverte automatique externe. La découverte automatique nécessite également des règles de publication pour l’URL des services Web Lync Server externes pour votre pool de directeurs et votre pool frontal. Pour plus d’informations sur la création de règles de publication sur le Web pour la découverte automatique, voir [configuration du proxy inverse pour la mobilité dans Lync Server 2013](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md).

Utilisez les procédures suivantes pour créer des règles de publication Web.

<div>


> [!NOTE]  
> Ces procédures présupposent que vous avez installé l’édition standard de Forefront Threat Management Gateway (TMG) 2010 ou que vous avez installé et configuré Internet Information Server avec l’extension de routage de requête d’application (IIS ARR). Vous utilisez TMG ou IIS ARR.



</div>

<div>

## <a name="to-create-a-web-server-publishing-rule-on-the-computer-running-tmg-2010"></a>Pour créer une règle de publication sur le serveur Web sur l’ordinateur exécutant TMG 2010

1.  Cliquez sur **Démarrer**, cliquez sur **programmes**, sélectionnez **Microsoft Forefront TMG**, puis cliquez sur **gestion de Forefront TMG**.

2.  Dans le volet gauche, développez **NomServeur**, cliquez avec le bouton droit sur **stratégie de pare-feu**, sélectionnez **nouveau**, puis cliquez sur règle de **publication de site Web**.

3.  Dans la page **Bienvenue dans la nouvelle règle de publication Web** , tapez un nom d’affichage pour la règle de publication (par exemple, LyncServerWebDownloadsRule).

4.  Dans la page **Sélectionner une action de règle** , sélectionnez **autoriser**.

5.  Dans la page **type de publication** , sélectionnez **publier un site Web ou un équilibrage de charge unique**.

6.  Dans la page sécurité de la **connexion au serveur** , sélectionnez **utiliser SSL pour se connecter au serveur Web publié ou à la batterie de**serveurs.

7.  Dans la page Détails de la **publication interne** , tapez le nom de domaine complet (FQDN) de la batterie de serveurs Web interne qui héberge le contenu de la réunion et le contenu de votre carnet d’adresses dans la zone **nom du site interne** .
    
    <div>
    

    > [!NOTE]  
    > Si votre serveur interne est un serveur Standard Edition Server, il s’agit du nom de domaine complet Standard Edition Server. S’il s’agit d’un pool frontal, il s’agit d’une adresse IP virtuelle d’équilibrage de charge matérielle qui charge les serveurs internes de batteries de serveurs. Le serveur TMG doit être en mesure de résoudre le nom de domaine complet sur l’adresse IP du serveur Web interne. Si le serveur TMG ne peut pas résoudre le nom de domaine complet (FQDN) en adresse IP correcte, vous pouvez sélectionner l’option <STRONG>utiliser un nom d’ordinateur ou une adresse IP pour vous connecter au serveur publié</STRONG>, puis, dans la zone nom de l' <STRONG>ordinateur ou</STRONG> <STRONG>adresse IP</STRONG> , tapez l’adresse IP du w interne. serveur EB. Dans ce cas, vous devez vous assurer que le port 53 est ouvert sur le serveur TMG et qu’il peut accéder à un serveur DNS résidant sur le réseau de périmètre. Vous pouvez également utiliser des entrées dans le fichier hosts local pour fournir une résolution de nom.

    
    </div>

8.  Dans la page Détails de la **publication interne** , dans la zone **chemin (facultatif)** , tapez ** / ** le chemin d’accès du dossier à publier.
    
    <div>
    

    > [!NOTE]  
    > Dans l’Assistant Publication de site Web, vous ne pouvez spécifier qu’un seul chemin. Vous pouvez ajouter des chemins supplémentaires en modifiant les propriétés de la règle.

    
    </div>

9.  Dans la page informations sur le **nom public** , confirmez que **ce nom de domaine** est sélectionné sous **accepter les demandes pour**, tapez le nom de domaine complet (FQDN) des services Web externes dans la zone **nom public** .

10. Dans la page **Sélectionner un écouteur Web** , cliquez sur **nouveau** pour ouvrir l’Assistant Nouvelle définition d’écoute Web.

11. Dans la page Bienvenue dans l' **Assistant Nouvelle écoute Web** , tapez un nom pour l’écouteur Web dans la zone **nom** de l’écouteur Web (par exemple, LyncServerWebServers).

12. Dans la page sécurité de la **connexion client** , sélectionnez **exiger des connexions SSL sécurisées avec les clients**.

13. Dans la page **adresse IP** de l’écouteur Web, sélectionnez **externe**, puis cliquez sur **Sélectionner des adresses IP**.

14. Dans la page de sélection de l' **écouteur externe** , sélectionnez **adresse IP spécifiée dans l’ordinateur Forefront TMG du réseau sélectionné**, sélectionnez l’adresse IP appropriée, puis cliquez sur **Ajouter**.

15. Sur la page **certificats SSL** de l’écouteur, sélectionnez **attribuer un certificat pour chaque adresse IP**, sélectionnez l’adresse IP associée au FQDN Web externe, puis cliquez sur **Sélectionner un certificat**.

16. Dans la page **Sélectionner un certificat** , sélectionnez le certificat correspondant aux noms publics spécifiés à l’étape 9, puis cliquez sur **Sélectionner**.

17. Dans la page **paramètres d’authentification** , sélectionnez **aucune authentification**.

18. Sur la page des **paramètres de connexion unique** , cliquez sur **suivant**.

19. Dans la page **fin de l’Assistant réception de Web** , vérifiez que les paramètres de l' **écouteur** sont corrects, puis cliquez sur **Terminer**.

20. Dans la page **délégation d’authentification** , sélectionnez **aucune délégation, mais le client pourra s’authentifier directement**.

21. Dans la page **jeu d’utilisateurs** , cliquez sur **suivant**.

22. Dans la page **fin de l’Assistant Nouvelle règle de publication Web** , vérifiez que les paramètres de règle de publication Web sont corrects, puis cliquez sur **Terminer**.

23. Cliquez sur **appliquer** dans le volet Détails pour enregistrer les modifications et mettre à jour la configuration.

</div>

<div>

## <a name="to-create-a-web-server-publishing-rule-on-the-computer-running-iis-arr"></a>Pour créer une règle de publication sur le serveur Web sur l’ordinateur exécutant IIS ARR

1.  Liez le certificat que vous allez utiliser pour le proxy inverse au protocole HTTPs. Cliquez sur **Démarrer**, cliquez sur **programmes**, sélectionnez **Outils d’administration**, puis cliquez sur **Gestionnaire des services Internet (IIS)**.
    
    <div>
    

    > [!NOTE]  
    > Des informations d’aide, des captures d’écran et des recommandations supplémentaires sur le déploiement et la configuration d’IIS ARR sont disponibles dans l’article NextHop <A href="http://go.microsoft.com/fwlink/?linkid=293391">à l’aide d’IIS ARR en tant que proxy inverse de Lync Server 2013</A>.

    
    </div>

2.  Si vous ne l’avez pas déjà fait, importez le certificat que vous utiliserez pour le proxy inverse. Dans le **Gestionnaire des services Internet (IIS)**, cliquez sur le nom du serveur proxy inverse à gauche de la console. Au milieu de la console sous **IIS** , recherchez **certificats de serveur**. Cliquez sur **certificats de serveur** avec le bouton droit, puis sélectionnez **ouvrir la fonctionnalité**.

3.  Sur le côté droit de la console, cliquez sur **Importer...**. Tapez le chemin d’accès et le nom du fichier du certificat portant l’extension ou cliquez sur **...** pour rechercher le certificat. Sélectionnez le certificat et cliquez sur **ouvrir**. Entrez le mot de passe utilisé pour protéger la clé privée (si vous avez attribué un mot de passe lors de l’exportation du certificat et de la clé privée). Cliquez sur **OK**. Si l’importation du certificat est réussie, le certificat apparaît comme entrée dans le milieu de la console en tant qu’entrée dans les **certificats de serveur**.

4.  Attribuez le certificat pour une utilisation par HTTPs. Sur le côté gauche de la console, sélectionnez le **site Web par défaut** du serveur IIS. Sur le côté droit, cliquez sur **liaisons...**. Dans la boîte de dialogue **liaisons de sites** , cliquez sur **Ajouter...**. Dans la boîte de dialogue **Ajouter une liaison de site** , sous **type:**, sélectionnez **https**. La sélection de https vous permet de sélectionner le certificat à utiliser pour HTTPS. Sous **certificat SSL:**, sélectionnez le certificat que vous avez importé pour le proxy inverse. Cliquez sur **OK**. Cliquez ensuite sur **Fermer**. Le certificat est désormais lié au proxy inverse pour SSL (Secure Socket Layer) et TLS (Transport Layer Security).
    
    <div>
    

    > [!IMPORTANT]  
    > Si vous recevez un message d’avertissement lors de la fermeture des boîtes de dialogue de liaison, il manque des certificats intermédiaires, vous devez localiser et importer le certificat d’autorité racine de l’autorité de certification publique et les certificats d’autorité de certification intermédiaires. Reportez-vous aux instructions de l’autorité publique qui vous a demandé votre certificat et suivez les instructions pour demander et importer une chaîne de certificats. Si vous avez exporté le certificat à partir de votre serveur Edge, vous pouvez exporter le certificat de l’autorité de certification racine et les certificats d’autorité de certification intermédiaires associés au serveur Edge. Importez le certificat racine de l’autorité de certification dans la Banque d’autorités de certification racine de l’ordinateur (à ne pas confondre avec le magasin de l’utilisateur).

    
    </div>

5.  Sur le côté gauche de la console sous le nom du serveur IIS, cliquez avec le bouton droit sur **batteries de serveurs** , puis cliquez sur créer une **batterie de serveurs.**
    
    <div>
    

    > [!NOTE]  
    > Si vous ne voyez pas le nœud <STRONG>batteries de serveurs</STRONG> , vous devez installer le routage de demandes d’application. Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">configuration de serveurs proxy inverse pour Lync Server 2013</A>.

    
    </div>
    
    Dans la boîte de dialogue **créer une batterie de serveurs** dans nom de la batterie de **serveurs**, tapez un nom (nom convivial pour les fins d’identification) pour la première URL. Cliquez sur **Suivant**.

6.  Dans la boîte de dialogue **Ajouter un serveur** dans **adresse du serveur**, tapez le nom de domaine complet (FQDN) des services Web externes sur votre serveur frontal. Les noms qui seront utilisés ici, par exemple, sont les mêmes que ceux utilisés dans la section planification du proxy inverse, du [proxy de certificat-proxy inverse dans Lync Server 2013](lync-server-2013-certificate-summary-reverse-proxy.md). Pour vous référer à la planification du proxy inverse, `webext.contoso.com`entrez le nom de domaine complet. Vérifiez que la case à cocher en regard de **connecté** est sélectionnée. Cliquez sur **Ajouter** pour ajouter le serveur à la liste de serveurs Web pour cette configuration.
    
    <div>
    

    > [!WARNING]  
    > Lync Server fait appel à des équilibreurs de charge matérielle pour le regroupement du Director et des serveurs frontaux pour le trafic HTTP et HTTPs. Vous devez fournir un nom de domaine complet uniquement lors de l’ajout d’un serveur à la batterie de serveurs IIS ARR. Le nom de domaine complet (FQDN) sera le serveur principal ou le directeur des configurations serveur hors pool ou le nom de domaine complet (FQDN) de l’équilibrage de charge matérielle configuré pour les pools de serveurs. La seule méthode prise en charge pour le trafic HTTP et HTTPs consiste à utiliser des équilibreurs de charge matérielle.

    
    </div>

7.  Dans la boîte de dialogue **Ajouter un serveur** , cliquez sur **Paramètres avancés.** Cette action ouvre une boîte de dialogue permettant de définir le routage de requête d’application pour les demandes de nom de domaine complet configuré. L’objectif est de redéfinir le port utilisé lors du traitement de la requête par IIS ARR.
    
    Par défaut, le port HTTP de destination doit être défini comme 8080. Cliquez sur en regard de la **80 port http** et définissez la valeur sur **8080**. Cliquez sur en regard de la **443 port HTTPS** et définissez la valeur sur **4443**. Laissez le paramètre **Weight** sur 100. Le cas échéant, vous pouvez redéfinir les pondérations pour une règle donnée une fois que vous avez des statistiques de référence. Cliquez sur **Terminer** pour terminer cette partie de la configuration de la règle.

8.  Il est possible qu’une boîte de dialogue de réécriture d’URL s’affiche pour vous informer que le gestionnaire des services Internet peut créer une règle de réécriture d’URL pour acheminer automatiquement toutes les demandes entrantes vers la batterie de serveurs. Cliquez sur **Oui**. Vous ajusterez les règles manuellement, mais le fait de sélectionner Yes définit la configuration initiale.

9.  Cliquez sur le nom de la batterie de serveurs que vous venez de créer. Sous **batterie de serveurs** dans l’affichage fonctionnalités du gestionnaire de services Internet, vous double-cliquez sur **mise en cache**. Désactivez l’option **activer le cache disque**. Cliquez sur **appliquer** sur le côté droit.

10. Cliquez sur le nom de la batterie de serveurs. Sous **batterie de serveurs** dans l’affichage fonctionnalités du gestionnaire de services Internet, vous double-cliquez sur **proxy**. Dans la page Paramètres du proxy, remplacez la valeur du délai d’expiration **(secondes)** par une valeur adaptée à votre déploiement. Cliquez sur **appliquer** pour enregistrer la modification.
    
    <div>
    

    > [!IMPORTANT]  
    > La valeur du délai d’expiration du proxy est un nombre qui peut varier d’un déploiement au déploiement. Nous vous conseillons de surveiller votre déploiement et de modifier la valeur de la meilleure utilisation pour les clients. Il est possible que vous puissiez définir la valeur sur une valeur inférieure ou égale à 200. Si vous prenez en charge des clients mobiles Lync dans votre environnement, définissez la valeur sur 960 pour autoriser les délais d’expiration de notifications de transmission d’Office 365 qui ont une valeur de délai d’expiration de 900. Il est très probable que vous deviez augmenter la valeur du délai d’expiration pour éviter que le client se déconnecte lorsque la valeur est trop faible ou que le nombre de connexions par le biais du proxy ne se déconnecte pas et qu’elle est désactivée longtemps après la déconnexion du client. Le fait de surveiller et de définir la position normale pour votre environnement est le seul moyen de déterminer où se trouve le paramètre approprié pour cette valeur.

    
    </div>

11. Cliquez sur le nom de la batterie de serveurs. Sous **batterie de serveurs** dans l’affichage fonctionnalités du gestionnaire de services Internet, vous double-cliquez sur **règles de routage**. Dans la boîte de dialogue Règles de routage sous routage, désactivez la case à cocher en regard de activer le déchargement SSL. Si vous ne pouvez pas désactiver la case à cocher, activez la case à cocher utiliser la réécriture **d’URL pour inspecter les demandes entrantes**. Cliquez sur **appliquer** pour enregistrer vos modifications.
    
    <div>
    

    > [!WARNING]  
    > Le déchargement SSL par le proxy inverse n’est pas pris en charge.

    
    </div>

12. Répétez les étapes 5-11 pour chaque URL qui doit traverser le proxy inverse. Une liste courante serait la suivante:
    
      - Services Web du serveur frontal externes: webext.contoso.com (déjà configurés par le biais du parcours initial)
    
      - Services Web de Director externes pour Director: webdirext.contoso.com (facultatif si un directeur est déployé)
    
      - URL simple: meet.contoso.com
    
      - Connexion simple pour les URL: dialin.contoso.com
    
      - URL de découverte automatique Lync: lyncdiscover.contoso.com
    
      - URL du serveur Office Web Apps: officewebapps01.contoso.com
        
        <div>
        

        > [!IMPORTANT]  
        > L’URL du serveur Office Web Apps utilisera une adresse port HTTPS différente. À l’étape 7, vous définissez <STRONG>port HTTPS</STRONG> comme <STRONG>443</STRONG> et <STRONG>port http</STRONG> en tant que port <STRONG>80</STRONG>. Les autres paramètres de configuration sont les mêmes.

        
        </div>

13. Sur le côté gauche de la console, cliquez sur le nom du serveur IIS. Au milieu de la console, repérez la réécriture d' **URL** sous **IIS**. Double-cliquez sur réécriture d’URL pour ouvrir la configuration des règles de réécriture d’URL. Vous devez voir les règles de chaque batterie de serveurs que vous avez créée lors des étapes précédentes. Si ce n’est pas le cas, vérifiez que vous avez cliqué sur le nom du **serveur IIS** juste en dessous du nœud de la **page de démarrage** dans la console du gestionnaire d’informations Internet.

14. Dans la boîte de dialogue de réécriture d' **URL** , en utilisant webext.contoso.com en guise d’exemple, le nom complet de la règle telle qu’affichée est **arr\_\_webext.contoso.com LoadBalance\_SSL**.
    
      - Double-cliquez sur la règle pour ouvrir la boîte de dialogue **modifier la règle de trafic entrant** .
    
      - Cliquez sur **Ajouter...** dans la boîte de dialogue **conditions** .
    
      - Sur la **condition ajouter** dans l’entrée de la **condition:** tapez **{http\_Host}**. (Lors de la saisie, une boîte de dialogue s’affiche pour vous permettre de sélectionner l’État). sous **vérifier si la chaîne d’entrée:** , sélectionnez **correspond au modèle**. Dans le type **\*** **d’entrée pattern** . **Ignorer la casse** doit être sélectionné. Cliquez sur **OK**.
    
      - Faites défiler la boîte de dialogue **modifier la règle de trafic entrant** pour rechercher la boîte de dialogue **action** . **Type d’action:** doit être défini sur **route vers la batterie de serveurs**, **schéma:** défini sur **https://**, **batterie de serveurs:** définie sur l’URL à laquelle s’applique cette règle. Pour cet exemple, ce doit être défini sur **webext.contoso.com**. **Path:** est défini sur **/{R: 0}**
    
      - Cliquez sur **appliquer** pour enregistrer vos modifications. Cliquez sur **retour aux règles** pour revenir aux règles de réécriture d’URL.

15. Répétez la procédure définie à l’étape 14 pour chacune des règles de réécriture SSL que vous avez définies, une pour chaque URL de batterie de serveurs.
    
    <div>
    

    > [!WARNING]  
    > Par défaut, les règles HTTP sont également créées et sont dénotées par leur appellation similaire aux règles SSL. Pour notre exemple actuel, la règle HTTP s’appelle <STRONG>ARR_webext. contoso. com _loadbalance</STRONG>. Il n’est pas nécessaire de modifier ces règles et celles-ci peuvent être ignorées en toute sécurité.

    
    </div>

</div>

<div>

## <a name="to-modify-the-properties-of-the-web-publishing-rule-in-tmg-2010"></a>Pour modifier les propriétés de la règle de publication Web dans TMG 2010

1.  Cliquez sur **Démarrer**, pointez sur **programmes**, sélectionnez **Microsoft Forefront TMG**, puis cliquez sur **gestion de Forefront TMG**.

2.  Dans le volet gauche, développez **NomServeur**, puis cliquez sur **stratégie de pare-feu**.

3.  Dans le volet Détails, cliquez avec le bouton droit sur la règle de publication sur le serveur Web que vous avez créée au cours de la procédure précédente (par exemple, LyncServerExternalRule), puis cliquez sur **Propriétés**.

4.  Dans la page **Propriétés** , sous l’onglet **de** , effectuez les opérations suivantes:
    
      - Dans la liste **cette règle s’applique au trafic de ces sources** , cliquez sur **n’importe où**, puis cliquez sur **supprimer**.
    
      - Cliquez sur **Ajouter**.
    
      - Dans **Ajouter des entités réseau**, développez **réseaux**, cliquez sur **externe**, cliquez sur **Ajouter**, puis sur **Fermer**.

5.  Dans l’onglet **à** , assurez-vous que la case à cocher **transférer l’en-tête de l’hôte d’origine au lieu de la** case à cocher réel est activée.

6.  Dans l’onglet **pontage** , activez la case à cocher rediriger la **demande vers le port SSL** , puis spécifiez le port **4443**.

7.  Dans l’onglet **nom du public** , ajoutez les URL simples (par exemple, meet.contoso.com et Dialin.contoso.com).

8.  Cliquez sur **appliquer** pour enregistrer les modifications, puis cliquez sur **OK**.

9.  Cliquez sur **appliquer** dans le volet Détails pour enregistrer les modifications et mettre à jour la configuration.

</div>

<div>

## <a name="to-modify-the-properties-of-the-web-publishing-rule-in-iis-arr"></a>Pour modifier les propriétés de la règle de publication Web dans IIS ARR

1.  Cliquez sur **Démarrer**, cliquez sur **programmes**, sélectionnez **Outils d’administration**, puis cliquez sur **Gestionnaire des services Internet (IIS)**.

2.  Sur le côté gauche de la console, cliquez sur le nom du serveur IIS.

3.  Au milieu de la console, repérez la réécriture d' **URL** sous **IIS**. Double-cliquez sur réécriture d’URL pour ouvrir la configuration des règles de réécriture d’URL.

4.  Double-cliquez sur la règle que vous devez modifier. Apportez les modifications souhaitées, selon les besoins, en fonction de l' **URL**, des **conditions**, des **variables serveur** ou de l' **action**.

5.  Cliquez sur **appliquer** pour valider les modifications. Cliquez sur **retour aux règles** pour modifier d’autres règles ou fermez la console du **Gestionnaire des services Internet** si vous avez effectué vos modifications.

</div>

</div>

<span> </span>

</div>

</div>

</div>

