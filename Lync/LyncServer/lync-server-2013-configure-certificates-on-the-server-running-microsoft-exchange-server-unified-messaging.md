---
title: "Conf. certif. sur le serv. exécutant la mess. un. Microsoft Exchange Server"
TOCtitle: "Conf. certif. sur le serv. exécutant la mess. un. Microsoft Exchange Server"
ms:assetid: 74c883b4-cef6-41a9-b2eb-7212be32fea4
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398564(v=OCS.15)
ms:contentKeyID: 49297741
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurer les certificats sur le serveur exécutant la messagerie unifiée Microsoft Exchange Server

 

_**Dernière rubrique modifiée :** 2016-12-08_

Si vous avez déployé la messagerie unifiée Exchange, comme indiqué dans [Planification de l’intégration de la messagerie unifiée Exchange dans Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) dans la documentation de planification, et que vous souhaitez fournir la messagerie unifiée Exchange aux utilisateurs Voix Entreprise de votre entreprise, vous pouvez utiliser les procédures suivantes pour configurer le certificat sur le serveur exécutant la messagerie unifiée Exchange.

> [!IMPORTANT]  
> Pour les certificats internes, les serveurs exécutant Lync Server 2013 et ceux exécutant Microsoft Exchange doivent tous deux avoir des certificats d’autorité de certification racine mutuellement approuvés. L’autorité de certification (AC) peut être identique ou différente, du moment que les serveurs ont le certificat racine de l’autorité de certification inscrit dans leur magasin de certificats d’autorités racines approuvés.

Le serveur Exchange Server doit être configuré avec un certificat de serveur pour pouvoir se connecter à Lync Server 2013 :

1.  Téléchargez le certificat d’autorité de certification du serveur Exchange Server.

2.  Installez le certificat d’autorité de certification du serveur Exchange Server.

3.  Vérifiez que l’autorité de certification figure dans la liste des autorités de certification racines de confiance du serveur Exchange Server.

4.  Créez une demande de certificat pour le serveur Exchange Server et installez le certificat.

5.  Assignez le certificat du serveur Exchange Server.

## Pour télécharger le certificat de l’autorité de certification

1.  Sur le serveur qui exécute la messagerie unifiée Exchange , cliquez sur **Démarrer**, sur **Exécuter**, tapez **http://\<nom du serveur CA émetteur\>/certsrv**, puis cliquez sur **OK**.

2.  Sous **Sélectionnez une tâche**, cliquez sur **Télécharger un certificat d’autorité de certification, une chaîne de certificats ou la liste de révocation de certificats**.

3.  Sous **Télécharger un certificat d’autorité de certification, une chaîne de certificats ou la liste de révocation de certificats**, sélectionnez **Méthode de codage Base 64**, puis cliquez sur **Télécharger un certificat de l’autorité de certification**.
    
    > [!NOTE]  
    > Vous pouvez également spécifier la méthode de codage DER (Distinguished Encoding Rules). Si vous sélectionnez cette méthode, le fichier spécifié à l’étape suivante de cette procédure et à l’étape 10 de la procédure <strong>Pour installer le certificat de l’autorité de certification</strong> sera de type .p7b et non .cer.

4.  Dans la boîte de dialogue **Téléchargement de fichier**, cliquez sur **Enregistrer**, puis enregistrez le fichier sur le disque dur du serveur (le fichier sera doté de l’extension .cer ou .p7b, selon la méthode de codage que vous avez sélectionnée à l’étape précédente).

## Pour installer le certificat de l’autorité de certification

1.  Sur le serveur qui exécute la messagerie unifiée Exchange, ouvrez la console MMC (Microsoft Management Console) en cliquant sur **Démarrer**, puis sur **Exécuter**, en tapant **mmc** dans la zone **Ouvrir**, puis en cliquant sur **OK**.

2.  Dans le menu **Fichier**, cliquez sur **Ajouter/Supprimer un composant logiciel enfichable**, puis sur **Ajouter**.

3.  Dans la zone **Ajout d’un composant logiciel enfichable autonome**, cliquez sur **Certificats**, puis sur **Ajouter**.

4.  Dans la boîte de dialogue **Composant logiciel enfichable Certificats**, cliquez sur **Compte d’ordinateur**, puis sur **Suivant**.

5.  Dans la boîte de dialogue **Sélectionner un ordinateur**, vérifiez que la case à cocher **Ordinateur local : (l’ordinateur sur lequel cette console s’exécute)** est activée, puis cliquez sur **Terminer**.

6.  Cliquez sur **Fermer**, puis sur **OK**.

7.  Dans l’arborescence de la console, développez **Certificats (ordinateur local)**, développez **Autorités de certification racines de confiance**, puis cliquez sur **Certificats**.

8.  Cliquez avec le bouton droit sur **Certificats**, cliquez sur **Toutes les tâches**, puis sur **Importer**.

9.  Cliquez sur **Suivant**.

10. Cliquez sur **Parcourir** pour localiser le fichier, puis cliquez sur **Suivant**. Le fichier sera doté de l’extension .cer ou .p7b, selon la méthode de codage sélectionnée à l’étape 3 de la procédure **Pour télécharger le certificat de l’autorité de certification**.

11. Cliquez sur **Placer tous les certificats dans le magasin suivant**.

12. Cliquez sur **Parcourir**, puis sélectionnez **Autorités de certification racines de confiance**.

13. Cliquez sur **Suivant** pour vérifier les paramètres, puis sur **Terminer**.

## Pour vérifier que l’autorité de certification figure sur la liste des autorités de certification racines de confiance

1.  Sur le serveur qui exécute la messagerie unifiée Exchange, dans la console MMC, développez **Certificats (ordinateur local)**, développez **Autorités de certification racines de confiance**, puis cliquez sur **Certificats**.

2.  Dans le volet de détail, vérifiez que votre autorité de certification figure sur la liste des autorités de certification de confiance.

## Pour configurer la messagerie unifiée Exchange Server 2013 avec Lync Server

1.  Pour plus d’informations, voir « Microsoft Lync Server 2013 » dans la documentation d’Exchange Server à l’adresse [http://go.microsoft.com/fwlink/?linkid=265372\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=265372%26clcid=0x40c).

## Pour créer une demande de certificat et installer le certificat sur Exchange Server 2007 (SP1)

1.  Sur le serveur qui exécute la messagerie unifiée Exchange , cliquez sur **Démarrer**, sur **Exécuter**, tapez **http://\<***nom du serveur CA émetteur***\>/certsrv**, puis cliquez sur **OK**.

2.  Sous **Sélectionner une tâche**, cliquez sur **Demander un certificat**.

3.  Sous **Demander un certificat**, cliquez sur **Demande de certificat avancée**.

4.  Sous **Demande de certificat avancée**, cliquez sur **Créer et soumettre une demande de certification auprès de cette Autorité de certification**.

5.  Sous **Demande de certificat avancée**, sélectionnez **Serveur web** ou un autre modèle de certificat du serveur configuré pour l’authentification du serveur.

6.  Dans **Informations d’identification pour les modèles hors connexion**, dans la zone **Nom**, tapez le nom de domaine complet (FQDN) du serveur Exchange Server.
    
    > [!NOTE]  
    > Vous devez entrer le nom de domaine complet du serveur Exchange Server pour que les communications fonctionnent.

7.  Sous **Options de la clé**, activez la case à cocher **Stocker le certificat dans le magasin de certificats de l’ordinateur local**.

8.  Cliquez sur le bouton **Envoyer** en bas de la page web.

9.  Dans la boîte de dialogue de confirmation qui s’affiche, cliquez sur **Oui**.

10. Dans la page Certificat émis, sous **Certificat émis**, cliquez sur **Installer ce certificat**.

11. Dans la boîte de dialogue de confirmation qui s’affiche, cliquez sur **Oui**.

12. Vérifiez que le message « Votre nouveau certificat a été correctement installé » s’affiche.

## Pour créer un certificat sur Exchange Server 2010

1.  Connectez-vous au serveur qui exécute la messagerie unifiée Exchange avec les droits d’utilisateurs appropriés. Pour plus d’informations, voir « Autorisations d’accès client » à l’adresse [http://go.microsoft.com/fwlink/?linkid=195499\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=195499%26clcid=0x40c).

2.  Suivez les procédures ci-après pour créer le certificat :
    
    1.  « Créer un certificat Exchange » à l’adresse [http://go.microsoft.com/fwlink/?linkid=195494\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=195494%26clcid=0x40c)
    
    2.  « Importer un certificat Exchange » à l’adresse [http://go.microsoft.com/fwlink/?linkid=195496\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=195496%26clcid=0x40c)
    
    > [!NOTE]  
    > Pour le <strong>Nom du sujet</strong> du certificat, vous devez entrer le nom de domaine complet du serveur Exchange Server pour que les communications fonctionnent.

## Pour attribuer le certificat au serveur Exchange Server 2007 (SP1)

1.  Sur le serveur qui exécute la messagerie unifiée Exchange, ouvrez la console MMC.

2.  Dans l’arborescence de la console, développez **Personnel** puis cliquez sur **Certificats**.

3.  Dans le volet de détail, vérifiez que le certificat personnel est bien affiché.

4.  Double-cliquez sur le certificat pour afficher ses détails et vérifier qu’il est valide.
    
    > [!NOTE]  
    > Cela peut prendre quelques minutes avant que le certificat s’affiche comme étant valide.

5.  Redémarrez le service de messagerie unifiée Microsoft Exchange.
    
    > [!NOTE]  
    > Le serveur qui exécute la messagerie unifiée Exchange Server 2007 SP1 récupère automatiquement le bon certificat.

6.  Ouvrez l’Observateur d’événements et recherchez l’ID de l’événement 1112. Il indique le certificat récupéré par le serveur exécutant la messagerie unifiée Exchange Server 2007 SP1.

## Pour attribuer le certificat au serveur Exchange Server 2010

1.  Connectez-vous au serveur qui exécute la messagerie unifiée Exchange avec les droits d’utilisateurs appropriés. Pour plus d’informations, voir « Autorisations d’accès client » à l’adresse [http://go.microsoft.com/fwlink/?linkid=195499\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=195499%26clcid=0x40c).

2.  Pour la procédure d’attribution du certificat, voir « Attribuer des services à un certificat » à l’adresse [http://go.microsoft.com/fwlink/?linkid=195497\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=195497%26clcid=0x40c).

