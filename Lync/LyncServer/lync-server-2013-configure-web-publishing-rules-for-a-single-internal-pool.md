---
title: "Lync Server 2013 : Con. des règles de publi. web pour un pool interne unique"
TOCTitle: Configuration des règles de publication web pour un pool interne unique
ms:assetid: 86ff4b2a-1ba9-46a2-a175-8b19e00a49dd
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg429712(v=OCS.15)
ms:contentKeyID: 49297975
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration des règles de publication web pour un pool interne unique dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Microsoft Forefront Threat Management Gateway 2010 et Internet Information Server Application Request Routing (IIS ARR) utilisent des règles de publication web afin de publier les ressources internes, telles qu’une URL de réunion, destinées utilisateurs d’Internet.

Outre les URL des services web pour les répertoires virtuels, vous devez également créer des règles de publication pour les URL simples, l’URL LyncDiscover et le serveur Office Web Apps Server. Pour chaque URL simple, vous devez créer une règle individuelle sur le proxy inverse qui pointe vers cette URL simple.

Si vous déployez la mobilité et que vous utilisez la découverte automatique, vous devez créer une règle de publication pour l’URL du service de découverte automatique externe. La découverte automatique nécessite également des règles de publication pour l’URL externe des services web Lync Server pour votre pool de directeurs et votre pool de serveurs frontaux. Pour plus d’informations sur la création des règles de publication web pour la découverte automatique, reportez-vous à [Configuration du proxy inverse pour la mobilité dans Lync Server 2013](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md).

Suivez les procédures ci-dessous pour créer des règles de publication web.

> [!NOTE]  
> Ces procédures supposent que vous avez installé la version Standard Edition de Forefront Threat Management Gateway (TMG) 2010, ou installé et configuré l’extension IIS ARR (Internet Information Server with the Application request Routing). Vous utilisez TMG ou IIS ARR.

## Pour créer une règle de publication de serveur web sur l’ordinateur qui exécute TMG 2010

1.  Cliquez sur **Démarrer** , sélectionnez **Programmes** , **Microsoft Forefront TMG** , puis cliquez sur **Forefront TMG Management** .

2.  Dans le volet de gauche, développez **NomServeur** , cliquez avec le bouton droit sur **Stratégie de pare-feu** , sélectionnez **Nouveau** , puis cliquez sur **Règle de publication web** .

3.  Dans la page **Assistant Nouvelle règle de publication web** , entrez un nom convivial pour la règle de publication (par exemple, LyncServerWebDownloadsRule).

4.  Dans la page **Sélectionner l’action de la règle** , sélectionnez **Autoriser** .

5.  Dans la page **Type de publication** , sélectionnez **Publier un seul site web ou équilibreur de charge** .

6.  Dans la page **Sécurité de connexion serveur** , sélectionnez **Utiliser SSL pour se connecter au serveur web publié ou à la batterie de serveurs** .

7.  Dans la page **Détails de publication interne** , tapez le nom de domaine complet de la batterie de serveurs web internes qui héberge le contenu de réunion et les fichiers de carnet d’adresses dans la zone **Nom du site interne** .
    
    > [!NOTE]  
    > Si votre serveur interne est un serveur Standard Edition, ce nom de domaine complet est celui du serveur Standard Edition. Si votre serveur interne est un pool frontal, le nom de domaine complet (FQDN) est une adresse IP virtuelle (VIP) de l’équilibreur de la charge matérielle qui équilibre la charge des serveurs de la batterie de serveurs web internes. Le serveur TMG doit pouvoir résoudre le nom de domaine complet sur l’adresse IP du serveur web interne. Si le serveur TMG n’est pas en mesure de résoudre le nom de domaine complet sur l’adresse IP correcte, vous pouvez sélectionner <strong>Utiliser un nom d’ordinateur ou une adresse IP pour se connecter au serveur publié</strong> , puis dans la zone <strong>Nom ou</strong> <strong>adresse IP de l’ordinateur</strong> , taper l’adresse IP du serveur web interne. Dans ce cas, vous devez vous assurer que le port 53 est ouvert sur le serveur TMG et que celui-ci parvient à atteindre un serveur DNS se trouvant dans le réseau de périmètre. Vous pouvez également utiliser des entrées dans le fichier hôtes local pour permettre la résolution des noms.

8.  Dans la page **Détails de publication interne** , dans la zone **Chemin d’accès (facultatif)** , tapez **/\*** comme chemin d’accès du dossier à publier.
    
    > [!NOTE]  
    > Dans l’Assistant de publication de sites web, vous ne pouvez indiquer qu’un seul chemin d’accès. Vous pouvez toutefois en ajouter d’autres en modifiant les propriétés de la règle.

9.  Dans la page **Informations sur les noms publics** , confirmez que **Ce nom de domaine** est bien sélectionné sous **Accepter les demandes pour** , et tapez le nom de domaine complet des services web externes dans la zone **Nom public** .

10. Dans la page **Sélectionnez le port d’écoute** , cliquez sur **Nouveau** pour ouvrir l’Assistant Nouvelle définition de port d’écoute web.

11. Dans la page **Assistant Nouveau port d’écoute web** , tapez le nom du port d’écoute web dans la zone **Nom du port d’écoute web** (par exemple, LyncServerWebServers).

12. Dans la page **Sécurité de la connexion client** , sélectionnez **Exiger des connexions sécurisées SSL avec les clients** .

13. Dans la page **Adresse IP de l’écouteur web** , sélectionnez **Externe** , puis cliquez sur **Sélectionner l’adresse IP** .

14. Dans la page **Sélection de l’adresse IP de l’écouteur externe** , sélectionnez **Les adresses IP spécifiées inscrites sur l’ordinateur Forefront TMG** qui sont dans le réseau sélectionné, sélectionnez l’adresse IP appropriée, puis cliquez sur **Ajouter** .

15. Dans la page **Certificats SSL de l’écouteur** , sélectionnez **Affecter un certificat à chaque adresse IP** , sélectionnez l’adresse IP associée au nom de domaine web complet externe, puis cliquez sur **Sélectionner le certificat** .

16. Dans la page **Sélectionner le certificat** , sélectionnez le certificat qui correspond aux noms publics spécifiés à l’étape 9, puis cliquez sur **Sélectionner** .

17. Dans la page **Paramètre d’authentification** , sélectionnez **Pas d’authentification** .

18. Dans la page **Paramètres de l’authentification unique** , cliquez sur **Suivant** .

19. Dans la page **Fin de l’Assistant Nouveau port d’écoute web** , vérifiez que les paramètres du **port d’écoute web** sont corrects, puis cliquez sur **Terminer** .

20. Dans la page **Délégation de l’authentification** , sélectionnez **Aucune délégation pour laisser le client s’authentifier directement** .

21. Dans la page **Ensemble d’utilisateurs** , cliquez sur **Suivant** .

22. Dans la page **Fin de l’Assistant Nouvelle règle de publication web** , vérifiez que les paramètres de la règle de publication web sont corrects, puis cliquez sur **Terminer** .

23. Cliquez sur **Appliquer** dans le volet des détails pour enregistrer les modifications et mettre à jour la configuration.

## Pour créer une règle de publication de serveur web sur l’ordinateur qui exécute IIS ARR

1.  Liez le certificat que vous utiliserez pour le proxy inverse au protocole HTTPS. Cliquez sur **Démarrer** , sélectionnez **Programmes** , **Outils d’administration** , puis cliquez sur **Gestionnaire des services Internet (IIS)** .
    
    > [!NOTE]  
    > L’article NextHop <a href="http://go.microsoft.com/fwlink/?linkid=293391">Using IIS ARR as a Reverse Proxy for Lync Server 2013 (Utilisation d’IIS ARR comme proxy inverse pour Lync Server 2013)</a> inclut des informations d’aide, des captures d’écran et des instructions supplémentaires sur le déploiement et la configuration d’IIS ARR.

2.  Si vous ne l’avez pas déjà fait, importez le certificat que vous utiliserez pour le proxy inverse. Dans le **Gestionnaire des services Internet (IIS)** , cliquez sur le nom du serveur proxy inverse dans la partie gauche de la console. Dans la partie centrale de la console, sous **Services Internet (IIS)**, recherchez **Certificats de serveur** . Cliquez avec le bouton droit sur **Certificats de serveur** , puis sélectionnez **Ouvrir la fonctionnalité** .

3.  Dans la partie droite de la console, cliquez sur **Importer** . Tapez le chemin d’accès et le nom de fichier du certificat avec son extension, ou cliquez sur **…** pour rechercher le certificat. Sélectionnez le certificat, puis cliquez sur **Ouvrir** . Indiquez le mot de passe utilisé pour protéger la clé privée (si vous avez affecté un mot de passe lors de l’exportation du certificat et de la clé privée). Cliquez sur **OK** . Si l’importation a réussi, le certificat s’affiche dans la partie centrale de la console sous la forme d’une entrée dans **Certificats de serveur** .

4.  Affectez le certificat utilisé par le protocole HTTPS. Dans la partie gauche de la console, sélectionnez le **site web par défaut** du serveur des services Internet (IIS). Dans la partie droite, cliquez sur **Liaisons** . Dans la boîte de dialogue **Liaisons de sites** , cliquez sur **Ajouter** . Dans la boîte de dialogue **Ajouter la liaison de site** , sous **Type** , sélectionnez **https** . La sélection de https vous permet de sélectionner le certificat à utiliser pour le protocole https. Sous **Certificat SSL** , sélectionnez le certificat que vous avez importé pour le proxy inverse. Cliquez sur **OK** , puis sur **Fermer** . Le certificat est à présent lié au proxy inverse pour les protocoles SSL (Secure Socket Layer) et TLS (Transport Layer Security).
    
    > [!IMPORTANT]  
    > Si vous recevez un message d’avertissement indiquant que les certificats intermédiaires sont manquants lorsque vous fermez les boîtes de dialogue Liaisons, vous devez rechercher et importer le certificat d’autorité racine d’une autorité de certification publique et les certificats d’autorité de certification intermédiaires. Consultez les instructions de l’autorité de certification publique auprès de laquelle vous avez demandé le certificat et suivez les instructions relatives à la demande et à l’importation d’une chaîne de certificats. Si vous avez exporté le certificat à partir de votre serveur Edge, vous pouvez exporter le certificat d’autorité de certification racine et les certificats d’autorité de certification intermédiaires associés au serveur Edge. Importez le certificat d’autorité de certification racine dans le magasin Autorités de certification racines de confiance de l’ordinateur (à ne pas confondre avec le magasin d’utilisateurs) et les certificats intermédiaires dans le magasin Autorités de certification intermédiaires de l’ordinateur.

5.  Dans la partie gauche de la console, sous le nom du serveur des services Internet (IIS), cliquez avec le bouton droit sur **Batteries de serveurs** , puis sur **Créer une batterie de serveurs** .
    
    > [!NOTE]  
    > Si le nœud <strong>Batteries de serveurs</strong> ne s’affiche pas, vous devez installer Application Request Routing. Pour plus d’informations, reportez-vous à <a href="lync-server-2013-setting-up-reverse-proxy-servers.md">Configuration des serveurs proxy inverses pour Lync Server 2013</a>.    
    
    
    Dans la boîte de dialogue **Créer une batterie de serveurs** , dans **Nom de la batterie de serveurs** , tapez un nom (par exemple, nom convivial pour faciliter l’identification) pour la première URL. Cliquez sur **Suivant** .

6.  Dans la boîte de dialogue **Ajouter un serveur** , dans **Adresse du serveur** , tapez le nom de domaine complet (FQDN) des services web externes sur votre serveur frontal. Les noms utilisés ici à titre d’exemple sont également utilisés dans la section Planification pour le proxy inverse ( [Résumé des certificats - Proxy inverse dans Lync Server 2013](lync-server-2013-certificate-summary-reverse-proxy.md)). Le nom de domaine complet (FQDN) `webext.contoso.com` a été entré pour la planification du proxy inverse. Vérifiez que la case à cocher en regard de **En ligne** est activée. Cliquez sur **Ajouter** pour ajouter le serveur au pool de serveurs web pour cette configuration.
    
    > [!WARNING]  
    > Lync Server utilise des programmes d’équilibrage de la charge matérielle pour regrouper les serveurs frontaux et directeur pour le trafic HTTP et HTTPS. Vous ne devez indiquer qu’un nom de domaine complet lorsque vous ajoutez un serveur à la batterie de serveurs IIS ARR. Le nom de domaine complet correspondra au serveur frontal ou au directeur dans les configurations de serveurs non regroupés, ou au programme d’équilibrage de la charge matérielle configuré pour les pools de serveurs. La seule méthode d’équilibrage de la charge du trafic HTTP et HTTPS prise en charge consiste à utiliser des programmes d’équilibrage de la charge matérielle.

7.  Dans la boîte de dialogue **Ajouter un serveur** , cliquez sur **Paramètres avancés** . La boîte de dialogue qui s’ouvre permet de définir le routage des demandes d’application pour les demandes adressées au nom de domaine complet configuré. L’objectif est de redéfinir le port utilisé lors du traitement de la demande par IIS ARR.
    
    Par défaut, le port HTTP de destination doit être défini sur 8080. Cliquez sur Suivant en regard de la valeur **httpPort 80** actuelle et définissez celle-ci sur **8080** . Cliquez sur Suivant en regard de la valeur **httpsPort 443** actuelle et définissez celle-ci sur **4443** . Laissez le paramètre **poids** défini sur 100. Au besoin, vous pouvez redéfinir le poids d’une règle une fois que vous disposez des statistiques de base. Cliquez sur **Terminer** pour terminer cette partie de la configuration des règles.

8.  Il est possible qu’une boîte de dialogue Règles de réécriture s’affiche pour vous informer que le Gestionnaire des services Internet (IIS) peut créer une règle de réécriture d’URL pour router automatiquement toutes les demandes entrantes vers la batterie de serveurs. Cliquez sur **Oui** . Vous devez ajuster les règles manuellement, mais sachez que la sélection de l’option Oui définit la configuration initiale.

9.  Cliquez sur le nom de la batterie de serveurs que vous venez de créer. Sous **Batterie de serveurs** dans l’affichage des fonctionnalités du Gestionnaire des services Internet (IIS), double-cliquez sur **Mise en cache** . Désactivez **Activer le cache disque** . Cliquez sur **Appliquer** dans la partie droite.

10. Cliquez sur le nom de la batterie de serveurs. Sous **Batterie de serveurs** dans l’affichage des fonctionnalités du Gestionnaire des services Internet (IIS), double-cliquez sur **Proxy** . Dans la page Paramètres proxy, remplacez la valeur de **Délai d’attente (secondes)** par une valeur appropriée à votre déploiement. Cliquez sur **Appliquer** pour enregistrer la modification.
    
    > [!IMPORTANT]  
    > La valeur de délai d’attente du proxy varie d’un déploiement à l’autre. Vous devez surveiller votre déploiement et modifier cette valeur pour fournir la meilleure expérience aux clients. Vous devez la définir au moins sur 200. Si votre environnement prend en charge les clients mobiles Lync, vous devez la définir sur 960 pour autoriser la temporisation des notifications push d’Office 365 ayant 900 pour valeur de délai d’attente. Vous devrez probablement l’augmenter pour éviter que le client ne se déconnecte lorsque la valeur est trop faible ou la réduire si les connexions établies via le proxy ne se déconnectent et ne disparaissent pas une fois le client déconnecté. Seules la planification et la surveillance des valeurs normales pour votre environnement permettent de déterminer le réglage adapté à cette valeur.

11. Cliquez sur le nom de la batterie de serveurs. Sous **Batterie de serveurs** dans l’affichage des fonctionnalités du Gestionnaire des services Internet (IIS), double-cliquez sur **Règles de routage** . Dans la boîte de dialogue Règles de routage, sous Routage, désactivez la case à cocher en regard de Activer le déchargement SSL. Si vous ne pouvez pas le faire, activez la case à cocher **Utiliser la réécriture d’URL pour inspecter les demandes entrantes** . Cliquez sur **Appliquer** pour enregistrer vos modifications.
    
    > [!CAUTION]  
    > Le déchargement SSL via le proxy inverse n’est pas pris en charge.

12. Répétez les étapes 5 à 11 pour chaque URL devant passer par le proxy inverse. Les valeurs suivantes sont représentatives d’une liste type :
    
      - Services web externes de serveur frontal : webext.contoso.com (déjà configuré par la procédure initiale)
    
      - Services web externes de directeur pour le directeur : webdirext.contoso.com (facultatif si un directeur est déployé)
    
      - URL simple de type Meet : meet.contoso.com
    
      - URL simple de type Dialin : dialin.contoso.com
    
      - URL de la découverte automatique de Lync : lyncdiscover.contoso.com
    
      - URL d’Office Web Apps Server : officewebapps01.contoso.com
        
        > [!IMPORTANT]  
        > L’URL du serveur Office Web Apps Server utilisera une autre adresse httpsPort. Dans l’étape 7, vous avez défini <strong>httpsPort</strong> sur la valeur <strong>443</strong> et <strong>httpPort</strong> sur la valeur <strong>80</strong> . Tous les autres paramètres de configuration sont identiques.

13. Dans la partie gauche de la console, cliquez sur le nom du serveur des services Internet (IIS). Dans la partie centrale de la console, recherchez **Réécriture d’URL** sous **Services Internet (IIS)**. Double-cliquez sur Réécriture d’URL pour ouvrir la configuration des règles de réécriture d’URL. Vous devez voir les règles de chaque batterie de serveurs créées au cours des étapes précédentes. Si ce n’est pas le cas, vérifiez que vous avez cliqué sur le nom de **serveur des services Internet (IIS)** situé immédiatement sous le nœud **Page de démarrage** dans la console du Gestionnaire des services Internet (IIS).

14. Dans la boîte de dialogue **Réécriture d’URL** , avec l’exemple webext.contoso.com, le nom complet de la règle telle qu’il est affiché est **ARR\_webext.contoso.com\_loadbalance\_SSL** .
    
      - Double-cliquez sur la règle pour ouvrir la boîte de dialogue **Modifier la règle de trafic entrant** .
    
      - Dans la boîte de dialogue **Conditions** , cliquez sur **Ajouter** .
    
      - Dans **Ajouter une condition** , dans **Saisie de la condition** , tapez **{HTTP\_HOST}** . (Pendant que vous tapez, une boîte de dialogue s’affiche pour vous permettre de sélectionner la condition). Sous **Vérifier si la chaîne de saisie** , sélectionnez **correspond au modèle** . Dans **Saisie du modèle** , tapez **\*** . L’option **Ignorer la casse** doit être sélectionné. Cliquez sur **OK** .
    
      - Faites défiler la page vers le bas dans la boîte de dialogue **Modifier la règle de trafic entrant** pour rechercher la boîte de dialogue **Action** . Le champ **Type d’action** doit être défini sur **Router vers la batterie de serveurs** , **Schéma** sur **https://** et **Batterie de serveurs** sur l’URL à laquelle cette règle s’applique. Pour cet exemple, la valeur doit être définie sur **webext.contoso.com** . **Chemin d’accès** est défini sur **/{R:0}**
    
      - Cliquez sur **Appliquer** pour enregistrer vos modifications. Cliquez sur **Retour aux règles** pour revenir aux règles de réécriture d’URL.

15. Répétez la procédure définie à l’étape 14 pour les règles de réécriture de SSL que vous avez définies (une par URL de batterie de serveurs).
    
    > [!WARNING]  
    > Par défaut, les règles HTTP sont également créées et peuvent être identifiées par le nom semblable à celui affecté aux règles SSL. Pour notre exemple, la règle HTTP serait nommée <strong>ARR_webext.contoso.com_loadbalance</strong> . Il n’est pas nécessaire de modifier ces règles : celles-ci peuvent être ignorées en toute sécurité.

## Pour modifier les propriétés de la règle de publication web dans TMG 2010

1.  Cliquez sur **Démarrer** , pointez sur **Programmes** , sélectionnez **Microsoft Forefront TMG** , puis cliquez sur **Forefront TMG Management** .

2.  Dans le volet de gauche, développez **NomServeur** , puis cliquez sur **Stratégie de pare-feu** .

3.  Dans le volet des détails, cliquez avec le bouton droit sur la règle de publication de serveur web que vous avez créée précédemment (par exemple, LyncServerExternalRule), puis cliquez sur **Propriétés** .

4.  Dans la page **Propriétés** , sous l’onglet **De** , procédez comme suit :
    
      - Dans la liste **Cette règle s’applique au trafic émanant de ces sources** , cliquez sur **Partout** , puis sur **Supprimer** .
    
      - Cliquez sur **Ajouter** .
    
      - Dans la boîte de dialogue **Ajouter des entités réseau** , développez **Réseaux** , cliquez sur **Externe** , puis sur **Ajouter** , puis sur **Fermer** .

5.  Sous l’onglet **À** , vérifiez que la case à cocher **Transmettre l’en-tête de l’hôte d’origine plutôt que l’en-tête réel** est activée.

6.  Dans la zone **Pontage** , activez la case à cocher **Rediriger la demande vers le port SSL** , puis spécifiez le port **4443** .

7.  Sous l’onglet **Nom public** , ajoutez les URL simples (par exemple, meet.contoso.com et dialin.contoso.com).

8.  Cliquez sur **Appliquer** pour enregistrer les modifications, puis sur **OK** .

9.  Cliquez sur **Appliquer** dans le volet des détails pour enregistrer les modifications et mettre à jour la configuration.

## Pour modifier les propriétés de la règle de publication web dans IIS ARR

1.  Cliquez sur **Démarrer** , sélectionnez **Programmes** , **Outils d’administration** , puis cliquez sur **Gestionnaire des services Internet (IIS)** .

2.  Dans la partie gauche de la console, cliquez sur le nom du serveur des services Internet (IIS).

3.  Dans la partie centrale de la console, recherchez **Réécriture d’URL** sous **Services Internet (IIS)**. Double-cliquez sur Réécriture d’URL pour ouvrir la configuration des règles de réécriture d’URL.

4.  Double-cliquez sur la règle que vous devez modifier. Apportez les modifications utiles dans **Reproduire l’URL** , **Conditions** , **Variables serveur** ou **Action** .

5.  Cliquez sur **Appliquer** pour valider vos modifications. Cliquez sur **Retour aux règles** pour modifier les autres règles ou fermez la console du **Gestionnaire des services Internet (IIS)** si vous avez terminé.

