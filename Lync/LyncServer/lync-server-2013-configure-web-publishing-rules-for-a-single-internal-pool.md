---
title: 'Lync Server 2013 : configuration des règles de publication Web pour un pool interne unique'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure web publishing rules for a single internal pool
ms:assetid: 86ff4b2a-1ba9-46a2-a175-8b19e00a49dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429712(v=OCS.15)
ms:contentKeyID: 48184725
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d87e0096ee71fb08da396188d419e918f66e125
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048057"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-web-publishing-rules-for-a-single-internal-pool-in-lync-server-2013"></a>Configurer des règles de publication Web pour un pool interne unique dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-07-07_

Microsoft Forefront Threat Management Gateway 2010 et Internet Information Server application Request Routing (IIS ARR) utilise des règles de publication Web pour publier des ressources internes, telles qu’une URL de réunion, aux utilisateurs sur Internet.

En plus des URL des services Web pour les répertoires virtuels, vous devez également créer des règles de publication pour les URL simples, l’URL LyncDiscover et le serveur Office Web Apps. Pour chaque URL simple, vous devez créer une règle individuelle sur le proxy inverse qui pointe sur cette URL simple.

Si vous déployez la mobilité et que vous utilisez la découverte automatique, vous devez créer une règle de publication pour l’URL du service de découverte automatique externe. La découverte automatique requiert également des règles de publication pour l’URL des services Web Lync Server externes pour votre pool directeur et votre pool frontal. Pour plus d’informations sur la création des règles de publication Web pour la découverte automatique, voir [configuration du proxy inverse pour la mobilité dans Lync Server 2013](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md).

Suivez les procédures ci-dessous pour créer des règles de publication web.

<div>


> [!NOTE]  
> Ces procédures supposent que vous avez installé l’édition standard de Forefront Threat Management Gateway (TMG) 2010 ou que vous avez installé et configuré Internet Information Server avec l’extension de routage des demandes d’application (IIS ARR). Vous utilisez TMG ou IIS ARR.



</div>

<div>

## <a name="to-create-a-web-server-publishing-rule-on-the-computer-running-tmg-2010"></a>Pour créer une règle de publication de serveur web sur l’ordinateur qui exécute TMG 2010

1.  Cliquez sur **Démarrer**, sélectionnez **Programmes**, **Microsoft Forefront TMG**, puis cliquez sur **Forefront TMG Management**.

2.  Dans le volet de gauche, développez **NomServeur**, cliquez avec le bouton droit sur **Stratégie de pare-feu**, sélectionnez **Nouveau**, puis cliquez sur **Règle de publication web**.

3.  Dans la page **Assistant Nouvelle règle de publication web**, entrez un nom convivial pour la règle de publication (par exemple, LyncServerWebDownloadsRule).

4.  Dans la page **Sélectionner l’action de la règle**, sélectionnez **Autoriser**.

5.  Dans la page **Type de publication**, sélectionnez **Publier un seul site web ou équilibreur de charge**.

6.  Dans la page **Sécurité de connexion serveur**, sélectionnez **Utiliser SSL pour se connecter au serveur web publié ou à la batterie de serveurs**.

7.  Dans la page **Détails de publication interne**, tapez le nom de domaine complet de la batterie de serveurs web internes qui héberge le contenu de réunion et les fichiers de carnet d’adresses dans la zone **Nom du site interne**.
    
    <div>
    

    > [!NOTE]  
    > Si votre serveur interne est un serveur Standard Edition, ce nom de domaine complet est celui du serveur Standard Edition. Si votre serveur interne est un pool frontal, le nom de domaine complet (FQDN) est une adresse IP virtuelle (VIP) de l’équilibreur de la charge matérielle qui équilibre la charge des serveurs de la batterie de serveurs web internes. Le serveur TMG doit pouvoir résoudre le nom de domaine complet sur l’adresse IP du serveur web interne. Si le serveur TMG ne parvient pas à résoudre le nom de domaine complet (FQDN) en adresse IP correcte, vous pouvez sélectionner <STRONG>utiliser un nom d’ordinateur ou une adresse IP pour se connecter au serveur publié</STRONG>, puis, dans la zone nom de l' <STRONG>ordinateur ou</STRONG> <STRONG>adresse IP</STRONG> , tapez l’adresse IP du serveur Web interne. Dans ce cas, vous devez vous assurer que le port 53 est ouvert sur le serveur TMG et que celui-ci parvient à atteindre un serveur DNS résidant dans le réseau de périmètre. Vous pouvez également utiliser des entrées dans le fichier hôtes local pour permettre la résolution des noms.

    
    </div>

8.  Sur la page **Détails de publication interne** , dans la zone **chemin d’accès (facultatif)** , tapez ** / ** comme chemin d’accès du dossier à publier.
    
    <div>
    

    > [!NOTE]  
    > Dans l’Assistant de publication de sites web, vous ne pouvez indiquer qu’un seul chemin d’accès. Vous pouvez toutefois en ajouter d’autres en modifiant les propriétés de la règle.

    
    </div>

9.  Dans la page **Informations sur les noms publics**, confirmez que **Ce nom de domaine** est bien sélectionné sous **Accepter les demandes pour**, et tapez le nom de domaine complet des services web externes dans la zone **Nom public**.

10. Dans la page **Sélectionnez le port d’écoute**, cliquez sur **Nouveau** pour ouvrir l’Assistant Nouvelle définition de port d’écoute web.

11. Dans la page **Assistant Nouveau port d’écoute web**, tapez le nom du port d’écoute web dans la zone **Nom du port d’écoute web** (par exemple, LyncServerWebServers).

12. Dans la page **Sécurité de la connexion client**, sélectionnez **Exiger des connexions sécurisées SSL avec les clients**.

13. Dans la page **Adresse IP de l’écouteur web**, sélectionnez **Externe**, puis cliquez sur **Sélectionner l’adresse IP**.

14. Dans la page **Sélection de l’adresse IP de l’écouteur externe**, sélectionnez **Les adresses IP spécifiées inscrites sur l’ordinateur Forefront TMG** qui sont dans le réseau sélectionné, sélectionnez l’adresse IP appropriée, puis cliquez sur **Ajouter**.

15. Dans la page **Certificats SSL de l’écouteur**, sélectionnez **Affecter un certificat à chaque adresse IP**, sélectionnez l’adresse IP associée au nom de domaine web complet externe, puis cliquez sur **Sélectionner le certificat**.

16. Dans la page **Sélectionner le certificat**, sélectionnez le certificat qui correspond aux noms publics spécifiés à l’étape 9, puis cliquez sur **Sélectionner**.

17. Dans la page **Paramètre d’authentification**, sélectionnez **Pas d’authentification**.

18. Dans la page **Paramètres de l’authentification unique**, cliquez sur **Suivant**.

19. Dans la page **Fin de l’Assistant Nouveau port d’écoute web**, vérifiez que les paramètres du **port d’écoute web** sont corrects, puis cliquez sur **Terminer**.

20. Dans la page **Délégation de l’authentification**, sélectionnez **Aucune délégation pour laisser le client s’authentifier directement**.

21. Dans la page **Ensemble d’utilisateurs**, cliquez sur **Suivant**.

22. Dans la page **Fin de l’Assistant Nouvelle règle de publication web**, vérifiez que les paramètres de la règle de publication web sont corrects, puis cliquez sur **Terminer**.

23. Cliquez sur **Appliquer** dans le volet des détails pour enregistrer les modifications et mettre à jour la configuration.

</div>

<div>

## <a name="to-create-a-web-server-publishing-rule-on-the-computer-running-iis-arr"></a>Pour créer une règle de publication de serveur Web sur l’ordinateur qui exécute IIS ARR

1.  Liez le certificat que vous allez utiliser pour le proxy inverse au protocole HTTPs. Cliquez sur **Démarrer**, sélectionnez **programmes**, **Outils d’administration**, puis **Gestionnaire des services Internet (IIS)**.
    
    <div>
    

    > [!NOTE]  
    > Une aide supplémentaire, des captures d’écran et des conseils sur le déploiement et la configuration d’IIS ARR se trouve dans l’article NextHop <A href="http://go.microsoft.com/fwlink/?linkid=293391">à l’aide d’IIS ARR en tant que proxy inverse pour Lync Server 2013</A>.

    
    </div>

2.  Si vous ne l’avez pas déjà fait, importez le certificat que vous utiliserez pour le proxy inverse. Dans le **Gestionnaire des services Internet (IIS)**, cliquez sur le nom du serveur proxy inverse dans la partie gauche de la console. Au milieu de la console, sous **IIS** , localisez les **certificats de serveur**. Cliquez avec le bouton droit sur **certificats de serveur** , puis sélectionnez **ouvrir la fonctionnalité**.

3.  Sur le côté droit de la console, cliquez sur **Importer...**. Tapez le chemin d’accès et le nom de fichier du certificat avec l’extension, ou cliquez sur **...** pour rechercher le certificat. Sélectionnez le certificat, puis cliquez sur **ouvrir**. Fournissez le mot de passe utilisé pour protéger la clé privée (si vous avez attribué un mot de passe lors de l’exportation du certificat et de la clé privée). Cliquez sur **OK**. Si l’importation de certificat a réussi, le certificat apparaît sous la forme d’une entrée au milieu de la console sous forme d’entrée dans les **certificats de serveur**.

4.  Affectez le certificat pour une utilisation par HTTPs. Sur le côté gauche de la console, sélectionnez le **site Web par défaut** du serveur IIS. Sur le côté droit, cliquez sur **liaisons...**. Dans la boîte de dialogue **liaisons de site** , cliquez sur **Ajouter.**... Dans la boîte de dialogue **Ajouter une liaison de site** , sous **type :**, sélectionnez **https**. La sélection du protocole HTTPS vous permet de sélectionner le certificat à utiliser pour HTTPS. Sous **certificat SSL :**, sélectionnez le certificat que vous avez importé pour le proxy inverse. Cliquez sur **OK**. Ensuite, cliquez sur **Fermer**. Le certificat est maintenant lié au proxy inverse pour SSL (Secure Socket Layer) et TLS (Transport Layer Security).
    
    <div>
    

    > [!IMPORTANT]  
    > Si vous recevez un avertissement lorsque vous fermez les boîtes de dialogue de liaison pour lesquelles des certificats intermédiaires sont manquants, vous devez rechercher et importer le certificat d’autorité racine de l’autorité de certification publique et tous les certificats de l’autorité de certification intermédiaire. Consultez les instructions de l’autorité de certification publique à partir de laquelle vous avez demandé votre certificat et suivez les instructions pour demander et importer une chaîne de certificats. Si vous avez exporté le certificat à partir de votre serveur Edge, vous pouvez exporter le certificat de l’autorité de certification racine et tous les certificats de l’autorité de certification intermédiaire associés au serveur Edge. Importez le certificat d’autorité de certification racine dans le magasin d’autorités de certification racines de confiance et les certificats intermédiaires dans le magasin d’autorités de certification intermédiaires de l’ordinateur (à ne pas confondre avec le magasin d’utilisateurs).

    
    </div>

5.  Sur le côté gauche de la console, sous le nom du serveur IIS, cliquez avec le bouton droit sur **batteries de serveurs** , puis cliquez sur créer une **batterie de serveurs...**.
    
    <div>
    

    > [!NOTE]  
    > Si vous ne voyez pas le nœud <STRONG>batteries de serveurs</STRONG> , vous devez installer le routage des demandes d’applications. Pour plus d’informations, voir <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up Reverse Proxy Servers for Lync Server 2013</A>.

    
    </div>
    
    Dans la boîte de dialogue **créer une batterie** de serveurs, dans nom de la **batterie de serveurs**, tapez le nom (il peut s’agir d’un nom convivial pour l’identification) pour la première URL. Cliquez sur **Suivant**.

6.  Dans la boîte de dialogue **Ajouter un serveur** dans **adresse du serveur**, tapez le nom de domaine complet (FQDN) des services Web externes sur votre serveur frontal. Les noms qui seront utilisés ici à titre d’exemple sont les mêmes que ceux utilisés dans la section de planification pour le proxy inverse, [Certificate Summary-Reverse Proxy in Lync Server 2013](lync-server-2013-certificate-summary-reverse-proxy.md). En vous référant à la planification du proxy inverse, nous `webext.contoso.com`allons taper le nom de domaine complet. Vérifiez que la case à cocher en regard de **en ligne** est activée. Cliquez sur **Ajouter** pour ajouter le serveur au pool de serveurs Web pour cette configuration.
    
    <div>
    

    > [!WARNING]  
    > Lync Server utilise des programmes d’équilibrage de la charge matérielle pour le directeur de pool et les serveurs frontaux pour le trafic HTTP et HTTPs. Vous ne fournissez qu’un seul nom de domaine complet lors de l’ajout d’un serveur à la batterie de serveurs IIS ARR. Le nom de domaine complet sera le serveur frontal ou le directeur dans les configurations de serveur non regroupé, ou le nom de domaine complet (FQDN) de l’équilibreur de charge matérielle configuré pour les pools de serveurs. La seule méthode prise en charge pour équilibrer la charge du trafic HTTP et HTTPs consiste à utiliser des programmes d’équilibrage de la charge matérielle.

    
    </div>

7.  Dans la boîte de dialogue **Ajouter un serveur** , cliquez sur **Paramètres avancés.**... Une boîte de dialogue s’ouvre pour définir le routage de demande d’application pour les demandes au nom de domaine complet configuré. L’objectif est de redéfinir le port utilisé lorsque la demande est traitée par IIS ARR.
    
    Par défaut, le port HTTP de destination doit être défini comme 8080. Cliquez sur en regard de la **httpPort 80** actuelle et définissez la valeur sur **8080**. Cliquez sur en regard de la **httpsPort 443** actuelle et définissez la valeur sur **4443**. Laissez le paramètre **Weight** à 100. Si nécessaire, vous pouvez redéfinir les pondérations d’une règle donnée une fois que vous avez défini les statistiques de la planification. Cliquez sur **Terminer** pour terminer cette partie de la configuration de la règle.

8.  Vous pouvez voir une boîte de dialogue de réécriture de règles qui vous informe que le gestionnaire des services Internet (IIS) peut créer une règle de réécriture d’URL pour acheminer automatiquement toutes les demandes entrantes vers la batterie de serveurs. Cliquez sur **Oui**. Vous allez ajuster les règles manuellement, mais la sélection de Oui définit la configuration initiale..

9.  Cliquez sur le nom de la batterie de serveurs que vous venez de créer. Sous **batterie de serveurs** dans l’affichage fonctionnalités du gestionnaire des services Internet (IIS), vous double-cliquez sur **mise en cache**. Désactivez l’option **activer le cache disque**. Cliquez sur **appliquer** à droite.

10. Cliquez sur le nom de la batterie de serveurs. Sous **batterie de serveurs** dans l’affichage fonctionnalités du gestionnaire des services Internet (IIS), vous double-cliquez sur **proxy**. Dans la page Paramètres du proxy, modifiez la valeur du délai d’expiration **(secondes)** en fonction de votre déploiement. Cliquez sur **appliquer** pour enregistrer la modification.
    
    <div>
    

    > [!IMPORTANT]  
    > La valeur du délai d’expiration du proxy est un nombre qui varie d’un déploiement à l’autre. Vous devez surveiller votre déploiement et modifier la valeur pour la meilleure expérience pour les clients. Vous pouvez définir la valeur sur 200. Si vous prenez en charge les clients mobiles Lync dans votre environnement, vous devez définir la valeur sur 960 pour autoriser le délai d’expiration des notifications de type transmission à partir d’Office 365, dont la valeur de délai d’expiration est de 900. Il est fort probable que vous deviez augmenter la valeur du délai d’expiration pour éviter que le client se déconnecte lorsque la valeur est trop faible ou réduire le nombre si les connexions par le proxy ne se déconnectent pas et s’effacent longtemps après la déconnexion du client. Surveillance et base-la définition de la normale pour votre environnement est la seule façon de déterminer où se trouve le paramètre correct pour cette valeur.

    
    </div>

11. Cliquez sur le nom de la batterie de serveurs. Sous **batterie de serveurs** dans l’affichage fonctionnalités du gestionnaire des services Internet (IIS), vous double-cliquez sur **règles de routage**. Dans la boîte de dialogue Règles de routage, sous routage, désactivez la case à cocher en regard de activer le déchargement SSL. Si la désactivation de cette case n’est pas disponible, activez la case à cocher **utiliser la réécriture d’URL pour inspecter les demandes entrantes**. Cliquez sur **appliquer** pour enregistrer vos modifications.
    
    <div>
    

    > [!WARNING]  
    > Le déchargement SSL par le proxy inverse n’est pas pris en charge.

    
    </div>

12. Répétez les étapes 5-11 pour chaque URL qui doit transiter par le proxy inverse. Une liste commune est la suivante :
    
      - Services Web de serveur frontal externes : webext.contoso.com (déjà configurés par la visite initiale)
    
      - Services Web Director externes pour Director : webdirext.contoso.com (facultatif si un directeur est déployé)
    
      - URL simple : meet.contoso.com
    
      - Numérotation URL simple : dialin.contoso.com
    
      - URL de découverte automatique Lync : lyncdiscover.contoso.com
    
      - URL d’Office Web Apps Server : officewebapps01.contoso.com
        
        <div>
        

        > [!IMPORTANT]  
        > L’URL du serveur Office Web Apps Server utilisera une autre adresse httpsPort. À l’étape 7, vous définissez le <STRONG>httpsPort</STRONG> en tant que <STRONG>443</STRONG> et le <STRONG>httpPort</STRONG> en tant que port <STRONG>80</STRONG>. Tous les autres paramètres de configuration sont les mêmes.

        
        </div>

13. Sur le côté gauche de la console, cliquez sur le nom du serveur IIS. Au milieu de la console, recherchez **URL Rewrite** sous **IIS**. Double-cliquez sur réécriture d’URL pour ouvrir la configuration des règles de réécriture d’URL. Vous devez voir les règles pour chaque batterie de serveurs que vous avez créée lors des étapes précédentes. Si vous ne le faites pas, vérifiez que vous avez cliqué sur le nom du **serveur IIS** juste en dessous du nœud de la **page de démarrage** dans la console du gestionnaire Internet Information Server.

14. Dans la boîte de dialogue de **réécriture d’URL** , à l’aide de webext.contoso.com comme exemple, le nom complet de la règle tel qu’il est affiché est **\_arr webext.contoso.com\_LoadBalance\_SSL**.
    
      - Double-cliquez sur la règle pour ouvrir la boîte de dialogue **modifier la règle de trafic entrant** .
    
      - Cliquez sur **Ajouter...** dans la boîte de dialogue **conditions** .
    
      - Dans la **condition Add** de l' **entrée de condition :** type **{\_http Host}**. (En fur et à mesure que vous tapez, une boîte de dialogue s’affiche pour vous permettre de sélectionner la condition). sous **Vérifier la chaîne d’entrée :** sélectionnez **correspond au modèle**. Dans le type **\*** **d’entrée pattern** . **Ignorer la casse** doit être sélectionné. Cliquez sur **OK**.
    
      - Faites défiler la boîte de dialogue **modifier la règle de trafic entrant** pour localiser la boîte de dialogue **action** . **Type d’action :** doit être défini sur **acheminer vers la batterie de serveurs**, **modèle :** défini sur **https://**, **batterie de serveurs :** définit sur l’URL à laquelle cette règle s’applique. Pour cet exemple, il doit être défini sur **webext.contoso.com**. **Path :** est défini sur **/{R : 0}**
    
      - Cliquez sur **appliquer** pour enregistrer vos modifications. Cliquez sur **retour aux règles** pour revenir aux règles de réécriture d’URL.

15. Répétez la procédure définie à l’étape 14 pour chacune des règles de réécriture SSL que vous avez définies, une par URL de batterie de serveurs.
    
    <div>
    

    > [!WARNING]  
    > Par défaut, les règles HTTP sont également créées et sont représentées par des noms similaires aux règles SSL. Pour notre exemple actuel, la règle HTTP est nommée <STRONG>ARR_webext. contoso. com_loadbalance</STRONG>. Aucune modification n’est requise pour ces règles et elles peuvent être ignorées en toute sécurité.

    
    </div>

</div>

<div>

## <a name="to-modify-the-properties-of-the-web-publishing-rule-in-tmg-2010"></a>Pour modifier les propriétés de la règle de publication Web dans TMG 2010

1.  Cliquez sur **Démarrer**, pointez sur **programmes**, sélectionnez **Microsoft Forefront TMG**, puis cliquez sur **Forefront TMG Management**.

2.  Dans le volet de gauche, développez **NomServeur**, puis cliquez sur **Stratégie de pare-feu**.

3.  Dans le volet des détails, cliquez avec le bouton droit sur la règle de publication de serveur web que vous avez créée précédemment (par exemple, LyncServerExternalRule), puis cliquez sur **Propriétés**.

4.  Dans la page **Propriétés**, sous l’onglet **De**, procédez comme suit :
    
      - Dans la liste **Cette règle s’applique au trafic émanant de ces sources**, cliquez sur **Partout**, puis sur **Supprimer**.
    
      - Cliquez sur **Ajouter**.
    
      - Dans la boîte de dialogue **Ajouter des entités réseau**, développez **Réseaux**, cliquez sur **Externe**, puis sur **Ajouter**, puis sur **Fermer**.

5.  Sous l’onglet **À**, vérifiez que la case à cocher **Transmettre l’en-tête de l’hôte d’origine plutôt que l’en-tête réel** est activée.

6.  Dans la zone **Pontage**, activez la case à cocher **Rediriger la demande vers le port SSL**, puis spécifiez le port **4443**.

7.  Sous l’onglet **Nom public**, ajoutez les URL simples (par exemple, meet.contoso.com et dialin.contoso.com).

8.  Cliquez sur **Appliquer** pour enregistrer les modifications, puis sur **OK**.

9.  Cliquez sur **Appliquer** dans le volet des détails pour enregistrer les modifications et mettre à jour la configuration.

</div>

<div>

## <a name="to-modify-the-properties-of-the-web-publishing-rule-in-iis-arr"></a>Pour modifier les propriétés de la règle de publication Web dans IIS ARR

1.  Cliquez sur **Démarrer**, sélectionnez **programmes**, **Outils d’administration**, puis **Gestionnaire des services Internet (IIS)**.

2.  Sur le côté gauche de la console, cliquez sur le nom du serveur IIS.

3.  Au milieu de la console, recherchez **URL Rewrite** sous **IIS**. Double-cliquez sur réécriture d’URL pour ouvrir la configuration des règles de réécriture d’URL.

4.  Double-cliquez sur la règle à modifier. Effectuez vos modifications, selon vos besoins, dans l' **URL de correspondance**, les **conditions**, les **variables de serveur** ou l' **action**.

5.  Cliquez sur **appliquer** pour valider vos modifications. Cliquez sur **retour aux règles** pour modifier d’autres règles ou fermez la console du **Gestionnaire IIS** si vous avez effectué vos modifications.

</div>

</div>

<span> </span>

</div>

</div>

</div>

