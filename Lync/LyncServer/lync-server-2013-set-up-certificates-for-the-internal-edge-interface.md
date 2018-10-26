---
title: 'Lync Server 2013 : Configuration des certificats pour l’interface interne Edge'
TOCTitle: Configuration des certificats pour l’interface interne Edge
ms:assetid: a1963cc9-87c5-4935-86c0-6bedc6afd0ac
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412750(v=OCS.15)
ms:contentKeyID: 49298404
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration des certificats pour l’interface interne Edge dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-11-07_

> [!IMPORTANT]  
> Lorsque vous exécutez l’Assistant Certificat, assurez-vous d’être connecté à l’aide d’un compte membre d’un groupe auquel ont été affectées les autorisations appropriées pour le type de modèle de certificat que vous utiliserez. Par défaut, une demande de certificat Lync Server 2013 utilise le modèle de certificat Serveur web. Si vous utilisez un compte membre du groupe RTCUniversalServerAdmins pour demander un certificat utilisant ce modèle, vérifiez que les autorisations Inscrire requises pour utiliser ce modèle ont été affectées au groupe.

Un seul certificat est requis sur l’interface interne de chaque serveur Edge. Les certificats de l’interface interne peuvent être émis par une autorité de certification d’entreprise interne (AC) ou une autorité de certification publique. Si votre organisation dispose d’une autorité de certification interne déployée, vous pouvez réaliser des économies sur l’utilisation de certificats publics en faisant appel à l’AC interne pour émettre le certificat de l’interface interne. Vous pouvez utiliser une AC interne Windows Server 2008 ou Windows Server 2008 R2 pour créer ces certificats.

Pour plus d’informations à ce sujet et sur les certificats requis, reportez-vous à [Certificats requis pour l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).

Pour configurer des certificats sur l’interface interne d’un serveur Edge au niveau d’un site, utilisez les procédures de cette section comme suit :

1.  Téléchargez la chaîne de certification de l’AC pour l’interface interne sur chaque serveur Edge.

2.  Importez la chaîne de certification de l’AC pour l’interface interne sur chaque serveur Edge.

3.  Créez la demande de certificat pour l’interface interne, sur un serveur Edge, appelé « premier serveur Edge ».

4.  Importez le certificat pour l’interface interne sur le premier serveur Edge.

5.  Importez le certificat sur les autres serveurs Edge du site (ou déployés derrière ce programme d’équilibrage de charge).

6.  Affectez le certificat pour l’interface interne de chaque serveur Edge.

Si vous avez plusieurs sites dotés de serveurs Edge (autrement dit, une topologie Edge sur plusieurs sites) ou des ensembles distincts de serveurs Edge déployés derrière différents programmes d’équilibrage de charge, vous devez exécuter ces étapes pour chaque site disposant de serveurs Edge et pour chaque ensemble de serveurs Edge déployé derrière un programme d’équilibrage de charge différent.

> [!NOTE]  
> Les étapes des procédures présentées dans cette section sont basées sur l’utilisation d’une autorité de certification Windows Server 2008, Windows Server 2008 R2, Windows Server 2012 ou Windows Server 2012 R2 pour créer un certificat pour chaque serveur Edge. Pour obtenir des instructions pas à pas pour toute autre autorité de certification, consultez la documentation de l’autorité de certification concernée. Par défaut, tous les utilisateurs authentifiés disposent des droits de l’utilisateur appropriés pour demander des certificats.<br />
Les procédures de cette section sont basées sur la création de demandes de certificats sur le serveur Edge dans le cadre du processus de déploiement Edge Server. Il est possible de créer des demandes de certificats à l’aide du serveur frontal. Cela vous permet d’achever la demande de certificat dès le début du processus de planification et de déploiement, avant de commencer le déploiement des serveurs Edge. Pour ce faire, vous devez vous assurer que le certificat demandé est défini avec une clé privée exportable.<br />
Les procédures de cette section décrivent l’utilisation d’un fichier .cer et d’un fichier .p7b pour le certificat. Si vous utilisez un type de fichier différent, modifiez ces procédures en conséquence.

## Pour télécharger la chaîne de certification de l’autorité de certification pour l’interface interne à l’aide du site web certsrv

1.  Ouvrez une session sur un serveur Lync Server 2013 du réseau interne (et non le serveur Edge) en tant que membre du groupe **Administrateurs** .

2.  Exécutez la commande suivante dans l’invite en cliquant sur **Démarrer** , **Exécuter** et en tapant la chaîne suivante :
    
        https://<name of your Issuing CA Server>/certsrv
    
    Exemple :
    
        https://ca01.contoso.net/certsrv
    
    > [!NOTE]  
    > Si vous utilisez une AC Windows Server 2008 ou Windows Server 2008 R2 Entreprise, vous devez employer https, et non http.

3.  Dans la page web certsrv de l’autorité de certification émettrice, sous **Sélectionnez une tâche** , cliquez sur **Télécharger un certificat d’autorité de certification, une chaîne de certificats ou la liste de révocation de certificats** .

4.  Sous **Télécharger un certificat d’autorité de certification, une chaîne de certificats ou la liste de révocation des certificats** , cliquez sur **Télécharger la chaîne du certificat de l’Autorité de certification** .

5.  Dans la boîte de dialogue **Téléchargement de fichier** , cliquez sur **Enregistrer** .

6.  Enregistrez le fichier .p7b sur le lecteur de disque dur du serveur, puis copiez-le dans un dossier sur chaque serveur Edge.
    
    > [!NOTE]  
    > Vérifiez que le fichier .p7b contient tous les certificats du chemin d’accès de certification. Pour afficher le chemin d’accès de certification, ouvrez le certificat de serveur et cliquez sur le chemin d’accès de certification.

## Pour exporter la chaîne de certification de l’autorité de certification pour l’interface interne à l’aide de la console MMC (Microsoft Management Console)

1.  Vous pouvez exporter le certificat racine de l’autorité de certification à partir de tout ordinateur joint au domaine à l’aide de la console MMC (Microsoft Management Console) ( Microsoft Management Console (MMC)). Cliquez sur **Démarrer** , sur **Exécuter** , puis tapez **MMC**.

2.  Dans la console MMC (Microsoft Management Console), cliquez sur **Fichier** , puis sur **Ajouter/Supprimer** .

3.  Dans la boîte de dialogue **Ajouter ou supprimer des composants logiciels enfichables** , sélectionnez **Certificats** , puis cliquez sur **Ajouter** . Dans l’invite, sélectionnez **Compte d’ordinateur** . Dans la boîte de dialogue **Sélectionner un ordinateur** , sélectionnez **Ordinateur local** . Cliquez sur **Terminer** . Cliquez sur **OK** .

4.  Développez **Certificats (Ordinateur local)** . Développez **Autorités de certification racines de confiance** , puis sélectionnez **Certificats** .

5.  Cliquez sur le certificat racine émis par votre autorité de certification. Cliquez avec le bouton droit sur le certificat, sélectionnez **Toutes les tâches** , puis **Exporter** . L’**Assistant Exportation du certificat** s’affiche.

6.  Dans l’**Assistant Exportation du certificat** , cliquez sur **Suivant** .

7.  Dans la boîte de dialogue **Format du fichier d’exportation** , sélectionnez le format de l’exportation. L’option recommandée est **Standard de syntaxe de message cryptographique - Certificats PKCS \#7 (.P7B)** . Si vous sélectionnez **Standard de syntaxe de message cryptographique - Certificats PKCS \#7 (.P7B)** , activez la case à cocher **Inclure tous les certificats dans le chemin d’accès de certification, si possible** pour exporter la chaîne de certificat, y compris le certificat d’autorité de certification racine et tout certificat d’autorité de certification intermédiaire. Cliquez sur **Suivant** .

8.  Dans la boîte de dialogue **Fichier à exporter** , dans l’entrée de nom de fichier, tapez un nom et un chemin d’accès de fichier (l’extension par défaut est .p7b) pour le certificat exporté. Si vous le souhaitez, cliquez sur **Parcourir** , recherchez un répertoire dans lequel placer le certificat exporté et spécifiez un nom pour le certificat exporté. Cliquez sur **Enregistrer** . Cliquez sur **Suivant** .

9.  Passez en revue le résumé des actions et cliquez sur **Terminer** pour achever l’exportation du certificat. Cliquez sur **OK** pour confirmer l’exportation.

## Pour importer la chaîne de certification de l’AC pour l’interface interne

1.  Sur chaque serveur Edge, ouvrez la console MMC (Microsoft Management Console) en cliquant sur **Démarrer** , puis sur **Exécuter** , en tapant **mmc** dans la zone **Ouvrir** , puis en cliquant sur **OK** .

2.  Dans le menu **Fichier** , cliquez sur **Ajouter/Supprimer un composant logiciel enfichable** , puis sur **Ajouter** .

3.  Dans la zone **Ajout d’un composant logiciel enfichable autonome** , cliquez sur **Certificats** , puis sur **Ajouter** .

4.  Dans la boîte de dialogue **Composant logiciel enfichable Certificats** , cliquez sur **Compte d’ordinateur** , puis sur **Suivant** .

5.  Dans la boîte de dialogue **Sélectionner un ordinateur** , assurez-vous que la case à cocher **Ordinateur local : (l’ordinateur sur lequel cette console s’exécute)** est activée, puis cliquez sur **Terminer** .

6.  Cliquez sur **Fermer** , puis sur **OK** .

7.  Dans l’arborescence de la console, développez **Certificats (ordinateur local)** , cliquez avec le bouton droit sur **Autorités de certification racines de confiance** , pointez sur **Toutes les tâches** , puis cliquez sur **Importer** .

8.  Dans l’Assistant, dans **Fichier à importer** , spécifiez le nom de fichier du certificat (qui correspond au nom indiqué lors du téléchargement de la chaîne de certification de l’AC pour l’interface interne dans la procédure précédente).

9.  Répétez cette procédure sur chaque serveur Edge.

## Pour créer la demande de certificat pour l’interface interne

1.  Sur l’un des serveurs Edge, démarrez l’Assistant Déploiement, et en regard de **Étape 3 : Demander, installer ou affecter les certificats** , cliquez sur **Exécuter** .
    
    > [!NOTE]  
    > Si plusieurs serveurs Edge d’un pool se trouvent à un même emplacement, vous pouvez exécuter l’Assistant Certificat sur n’importe lequel d’entre eux.<br />
    Après la première exécution de l’Étape 3, le bouton change et indique <strong>Réexécuter</strong> et une coche verte indiquant la fin de la tâche ne s’affiche qu’une fois que tous les certificats requis ont été demandés, installés et affectés.

2.  Dans la page **Tâches se rapportant aux certificats disponibles** , cliquez sur **Créer une demande de certificat** .

3.  Dans la page **Demande de certificat** , cliquez sur **Suivant** .

4.  Dans la page **Demandes différées ou immédiates** , cliquez sur **Préparer la demande, mais ne pas l’envoyer maintenant** .

5.  Dans la page **Fichier de demande de certificat** , tapez le chemin d’accès complet et le nom du fichier dans lequel la demande doit être enregistrée (par exemple, **c:\\cert\_internal\_edge.cer** ).

6.  Dans la page **Spécifier un autre modèle de certificat** , pour utiliser un autre modèle que le modèle Serveur web par défaut, activez la case à cocher **Utiliser un autre modèle de certificat pour l’autorité de certification sélectionnée** .

7.  Dans la page **Nom et paramètres de sécurité** , procédez comme suit :
    
      - Dans **Nom convivial** , tapez le nom complet du certificat (par exemple, Périmètre interne).
    
      - Dans **Longueur en bits** , spécifiez la longueur en bits (généralement, la valeur par défaut est **2048** ).
        
        > [!NOTE]  
        > Les longueurs en bits plus élevées offrent davantage de sécurité, mais nuisent à la vitesse.    
      - Si le certificat doit être exportable, activez la case à cocher **Marquer la clé privée du certificat comme exportable** .

8.  Dans la page **Informations relatives à l’organisation** , tapez le nom de l’organisation et de l’unité d’organisation (UO) (par exemple, une division ou un service).

9.  Dans la page **Informations géographiques** , spécifiez les informations d’emplacement.

10. Dans la page **Nom du sujet/Autres noms du sujet** , le système affiche les informations automatiquement renseignées par l’Assistant.

11. Dans la page **Configurer d’autres noms du sujet supplémentaires** , spécifiez les autres noms du sujet supplémentaires nécessaires.

12. Dans la page **Résumé de la demande** , examinez les informations relatives au certificat qui seront utilisées pour générer la demande.

13. Une fois les commandes terminées, procédez comme suit :
    
      - Pour afficher le fichier journal de la demande de certificat, cliquez sur **Afficher le journal** .
    
      - Pour terminer la demande de certificat, cliquez sur **Suivant** .

14. Dans la page **Fichier de demande de certificat** , procédez comme suit :
    
      - Pour afficher le fichier de demande de signature de certificat (CSR) généré, cliquez sur **Afficher** .
    
      - Pour fermer l’Assistant, cliquez sur **Terminer** .

15. Envoyez ce fichier à votre autorité de certification (par messagerie électronique ou un autre procédé pris en charge par votre organisation pour votre autorité de certification d’entreprise). Lorsque vous recevez le fichier de réponse, copiez le nouveau certificat sur cet ordinateur de sorte qu’il soit disponible pour l’importation.

## Pour importer le certificat pour l’interface interne

1.  Ouvrez une session sur le serveur Edge sur lequel vous avez créé la demande de certificat en tant que membre du groupe Administrateurs local.

2.  Dans l’Assistant Déploiement, en regard de l’**Étape 3 : Demander, installer ou affecter les certificats** , cliquez sur **Réexécuter** .
    
    Après la première exécution de l’Étape 3, le bouton change et indique **Réexécuter** , mais une coche verte (indiquant la fin de la tâche) ne s’affiche qu’une fois que tous les certificats requis ont été demandés, installés et affectés.

3.  Dans la page **Tâches se rapportant aux certificats disponibles** , cliquez sur **Importer un certificat à partir d’un fichier .P7b, .pfx ou .cer** .

4.  Dans la page **Importer un certificat** , tapez le chemin complet et le nom du fichier du certificat que vous avez demandé et reçu pour l’interface interne de ce serveur Edge (ou cliquez sur **Parcourir** pour rechercher et sélectionner le fichier).

5.  Si vous importez des certificats contenant une clé privée pour d’autres membres du pool, activez la case à cocher **Le fichier du certificat contient la clé privée du certificat** et spécifiez le mot de passe.

## Pour exporter le certificat avec la clé privée pour les serveurs Edge d’un pool

1.  Ouvrez une session en tant que membre du groupe Administrateurs sur le serveur Edge sur lequel vous avez importé le certificat.

2.  Cliquez sur **Démarrer** , sur **Exécuter** , puis tapez **MMC** .

3.  Dans la console MMC (Microsoft Management Console), cliquez sur **Fichier** , puis sur **Ajouter/Supprimer un composant logiciel enfichable** .

4.  Dans la page Ajouter ou supprimer des composants logiciels enfichables, cliquez sur **Certificats** , puis sur **Ajouter** .

5.  Dans la boîte de dialogue Composant logiciel enfichable Certificats, sélectionnez **Le compte de l’ordinateur** . Cliquez sur **Suivant** . Dans Sélectionner un ordinateur, sélectionnez **L’ordinateur local (l’ordinateur sur lequel cette console s’exécute)** . Cliquez sur **Terminer** . Cliquez sur **OK** pour terminer la configuration de la console MMC (Microsoft Management Console).

6.  Double-cliquez sur **Certificats (ordinateur local)** pour développer les magasins de certificats. Double-cliquez sur **Personnel** , puis sur **Certificats** .
    
    > [!IMPORTANT]  
    > Si aucun certificat ne se trouve dans le magasin personnel de certificats de l’ordinateur local, aucune clé privée n’est associée au certificat importé. Vérifiez la demande et la procédure d’importation. Si le problème persiste, contactez votre administrateur ou fournisseur d’autorités de certification.

7.  Dans le magasin personnel de certificats de l’ordinateur local, cliquez avec le bouton droit sur le certificat que vous exportez. Cliquez sur **Toutes les tâches** , puis sur **Exporter** .

8.  Dans l’Assistant Exportation du certificat, cliquez sur **Suivant** . Sélectionnez **Oui, exporter la clé privée** . Cliquez sur **Suivant** .
    
    > [!NOTE]  
    > Si la sélection <strong>Oui, exporter la clé privée</strong> n’est pas disponible, cela signifie que la clé privée associée au certificat n’était pas marquée pour l’exportation. Pour pouvoir poursuivre l’exportation, vous devrez faire une nouvelle demande de certificat en vous assurant que le certificat est marqué de façon à autoriser l’exportation de la clé privée. Contactez votre administrateur ou fournisseur d’autorités de certification.

9.  Dans la boîte de dialogue Exporter les formats de fichiers, sélectionnez **Échange d’informations personnelles – PKCS\#12 (.PFX)** , puis les éléments suivants :
    
      - Inclure tous les certificats dans le chemin d’accès de certification, si possible
    
      - Exporter toutes les propriétés étendues
        
        > [!WARNING]  
        > Lorsque vous exportez le certificat à partir d’un serveur Edge, ne sélectionnez pas <strong>Supprimer la clé privée si l’exportation s’est terminée correctement</strong> . Si vous sélectionnez cette option, vous serez obligé d’importer le certificat et la clé privée sur ce serveur Edge.    
    Cliquez sur **Suivant** pour continuer.

10. Si vous souhaitez affecter un mot de passe pour protéger la clé privée, tapez un mot de passe pour cette clé. Réentrez le mot de passe pour le confirmer. Cliquez sur **Suivant** .

11. Tapez un chemin d’accès et un nom de fichier avec l’extension .pfx pour le certificat exporté. Le chemin d’accès doit être accessible à tous les autres serveurs Edge du pool ou transportable au moyen d’un média amovible, comme par exemple, un disque mémoire flash USB. Cliquez sur **Suivant** .

12. Examinez le récapitulatif dans la boîte de dialogue Fin de l’Assistant Exportation du certificat. Cliquez sur **Terminer** .

13. Cliquez sur **OK** dans la boîte de dialogue indiquant que l’exportation a abouti.

14. Importez le fichier de certificat exporté dans les autres serveurs Edge en suivant les étapes décrites dans les procédures [Configuration des certificats pour l’interface Edge externe pour Lync Server 2013](lync-server-2013-set-up-certificates-for-the-external-edge-interface.md).

## Pour affecter le certificat à l’interface interne des serveurs Edge

1.  Sur chaque serveur Edge, dans l’Assistant Déploiement, à l’**Étape 3 : Demander, installer ou affecter les certificats** , cliquez sur **Réexécuter** .

2.  Dans la page **Tâches se rapportant aux certificats disponibles** , cliquez sur **Affecter un certificat existant** .

3.  Dans la page **Affectation de certificat** , sélectionnez **Serveur Edge interne** dans la liste.

4.  Dans la page **Magasin de certificats** , sélectionnez le certificat que vous avez importé pour l’interface interne du serveur Edge (procédure précédente).

5.  Dans la page **Résumé de l’affectation du certificat** , vérifiez vos paramètres, puis cliquez sur **Suivant** pour affecter les certificats.

6.  Dans la page de fin de l’Assistant, cliquez sur **Terminer** .

7.  Après avoir utilisé cette procédure pour affecter le certificat de l’interface interne du serveur Edge, ouvrez le module enfichable pour les certificats sur chaque serveur, développez **Certificats (ordinateur local)** , **Personnel** , cliquez sur **Certificats** , puis vérifiez dans le volet d’informations que le certificat de l’interface interne du serveur Edge figure dans la liste.

8.  Si votre déploiement inclut plusieurs serveurs Edge, répétez cette procédure pour chaque serveur Edge.

