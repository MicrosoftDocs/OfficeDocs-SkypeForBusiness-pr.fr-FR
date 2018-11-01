---
title: 'Lync Server 2013 : Configuration des certificats pour l’interface Edge externe'
TOCTitle: Configuration des certificats pour l’interface Edge externe
ms:assetid: 5d78182c-88d8-4483-95ad-74b17f2d5fac
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398409(v=OCS.15)
ms:contentKeyID: 49297344
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration des certificats pour l’interface Edge externe pour Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

> [!IMPORTANT]  
> Lorsque vous exécutez l’Assistant Certificat, assurez-vous d’être connecté à l’aide d’un compte membre d’un groupe auquel ont été affectées les autorisations appropriées pour le type de modèle de certificat que vous utiliserez. Par défaut, une demande de certificat Lync Server utilise le modèle de certificat Serveur web. Si vous utilisez un compte membre du groupe RTCUniversalServerAdmins pour demander un certificat utilisant ce modèle, vérifiez que les autorisations Inscrire requises pour utiliser ce modèle ont été affectées au groupe.

Chaque serveur Edge requiert un certificat public sur l’interface entre le réseau de périmètre et Internet, et l’autre nom de sujet du certificat doit contenir les noms externes du service Edge d’accès et les noms de domaine complets (FQDN) du service Edge de conférence web.

Pour plus d’informations à ce sujet et sur les certificats requis, reportez-vous à [Certificats requis pour l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).

Pour obtenir la liste des autorités de certification (CA) publiques fournissant des certificats conformes à certaines exigences pour les certificats de communications unifiées et ayant mis en place un partenariat avec Microsoft pour garantir leur fonctionnement avec l’Assistant Certificat Lync Server 2013, reportez-vous à l’article 929395 de la base de connaissances Microsoft, « Partenaires de certificat de communications unifiées pour Exchange Server et Communications Server », à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=202834](http://go.microsoft.com/fwlink/p/?linkid=202834).

## Configuration des certificats sur les interfaces externes

Pour configurer un certificat sur l’interface Edge externe d’un site, suivez les procédures décrites dans cette section afin d’effectuer les opérations suivantes :

  - Créer la demande de certificat pour l’interface externe du serveur Edge.

  - Envoyer la demande à votre autorité de certification publique.

  - Importer le certificat pour l’interface externe de chaque serveur Edge.

  - Affecter le certificat pour l’interface externe de chaque serveur Edge.

  - Si votre déploiement comporte plusieurs serveurs Edge, exportez le certificat avec sa clé privée, puis copiez-le sur les autres serveurs Edge. Ensuite, pour chaque serveur Edge, importez-le et affectez-le comme indiqué précédemment. Répétez cette procédure sur chaque serveur Edge.

Vous pouvez demander des certificats publics directement à une autorité de certification publique (par exemple, à partir de son site web). Les procédures décrites dans cette section utilisent l’Assistant Certificat pour la plupart des tâches relatives aux certificats. Si vous choisissez de demander un certificat directement à une autorité de certification publique, vous devrez modifier chaque procédure pour demander, transférer et importer le certificat, mais aussi pour importer la chaîne de certificats.

Lorsque vous demandez un certificat à une autorité de certification externe, les informations d’identification fournies doivent englober les droits de demande d’un certificat à cette autorité de certification. Chaque autorité de certification a une stratégie de sécurité qui spécifie les informations d’identification (à sareportez-vous à l’utilisateur spécifique et les noms de groupe) autorisées à demander, émettre, gérer ou lire des certificats.

Si vous décidez d’utiliser la console MMC (Microsoft Management Console) des certificats pour importer la chaîne de certificats et le certificat, vous devez les importer dans le magasin de certificats de l’ordinateur. Si vous les importez dans le magasin de certificats de l’utilisateur ou du service, le certificat ne pourra pas être affecté via l’Assistant Certificat Lync Server 2013.

## Pour créer la demande de certificat pour l’interface externe du serveur Edge

1.  Sur le serveur Edge, dans l’Assistant Déploiement, en regard de **Étape 3 : Demander, installer ou affecter les certificats** , cliquez sur **Réexécuter** .
    
    > [!NOTE]  
    > Si votre organisation souhaite prendre en charge la solution PIC avec AOL, vous ne pouvez pas utiliser l’Assistant Déploiement de Lync Server pour demander le certificat. Vous devez effectuer les procédures décrites à la section « Pour créer une demande de certificat pour l’interface externe du serveur Edge afin de prendre en charge la solution PIC avec AOL » dans la suite de cette rubrique.<br />
    Si plusieurs serveurs Edge se trouvent au même emplacement dans un pool, vous pouvez exécuter l’Assistant Certificat Lync Server 2013 sur n’importe lequel d’entre eux.

2.  Dans la page **Tâches se rapportant aux certificats disponibles** , cliquez sur **Créer une demande de certificat** .

3.  Dans la page **Demande de certificat** , cliquez sur **Certificat de serveur Edge externe** .

4.  Dans la page **Demande différée ou immédiate** , cochez la case **Préparer la demande maintenant, mais l’envoyer plus tard** .

5.  Dans la page **Fichier de demande de certificat** , tapez le chemin d’accès complet et le nom du fichier dans lequel la demande doit être enregistrée (par exemple, c:\\cert\_exernal\_edge.cer).

6.  Dans la page **Spécifier un autre modèle de certificat** , pour utiliser un autre modèle que le modèle WebServer par défaut, cochez la case **Utiliser un autre modèle de certificat pour l’autorité de certification sélectionnée** .

7.  Dans la page **Nom et paramètres de sécurité** , procédez comme suit :
    
      - Dans **Nom convivial** , tapez un nom d’affichage du certificat.
    
      - Dans **Longueur en bits** , spécifiez la longueur en bits (généralement, la valeur par défaut est **2048** ).
    
      - Vérifiez que la case **Marquer la clé privée du certificat comme exportable** est cochée.

8.  Dans la page **Informations relatives à l’organisation** , tapez le nom de l’organisation et de l’unité d’organisation (par exemple, une division ou un service).

9.  Dans la page **Informations géographiques** , spécifiez les informations d’emplacement.

10. Dans la page **Nom du sujet/Autres noms du sujet** , le système affiche les informations automatiquement renseignées par l’Assistant. Si d’autres noms du sujet doivent être ajoutés, spécifiez-les dans les deux étapes suivantes.

11. Dans la page **Paramètre du domaine SIP sur les autres noms du sujet** , activez la case à cocher du domaine pour ajouter une entrée sip. *\<sipdomain\>* (domaine SIP) à la liste des autres noms du sujet.

12. Dans la page **Configurer d’autres noms du sujet supplémentaires** , spécifiez les autres noms du sujet supplémentaires nécessaires.

13. Dans la page **Résumé de la demande** , vérifiez les informations de certificat à utiliser pour générer la demande.

14. Une fois que l’exécution des commandes est terminée, procédez comme suit :
    
      - Pour afficher le fichier journal de la demande de certificat, cliquez sur **Afficher le journal** .
    
      - Pour terminer la demande de certificat, cliquez sur **Suivant** .

15. Dans la page **Fichier de demande de certificat** , procédez comme suit :
    
      - Pour afficher le fichier de demande de signature de certificat (CSR) généré, cliquez sur **Afficher** .
    
      - Pour fermer l’Assistant, cliquez sur **Terminer** .

16. Copiez le fichier de sortie à un emplacement à partir duquel vous pouvez l’envoyer à l’autorité de certification publique.

## Pour créer une demande de certificat pour l’interface externe du serveur Edge afin de prendre en charge la connectivité PIC avec AOL

1.  Lorsque le modèle requis est à la disposition de l’autorité de certification, utilisez l’applet de commande Windows PowerShell suivante depuis le serveur Edge pour demander le certificat :
    
        Request-CsCertificate -New -Type AccessEdgeExternal  -Output C:\ <certfilename.txt or certfilename.csr>  -ClientEku $true -Template <template name>
    
    Le nom de certificat par défaut du modèle fourni dans Lync Server 2013 est Serveur web. Spécifiez uniquement *\<template name\>* (nom du modèle) si vous devez utiliser un modèle différent du modèle par défaut.
    
    > [!NOTE]  
    > Si votre organisation souhaite prendre en charge la solution PIC avec AOL, vous devez utiliser Windows PowerShell au lieu de l’Assistant Certificat afin de demander le certificat à affecter au serveur Edge externe pour le service Edge d’accès. Cela est dû au fait que le modèle Serveur web Lync Server 2013 utilisé par l’Assistant Certificat pour demander un certificat ne prend pas en charge la configuration EKU (utilisation avancée de la clé) sur le client. Avant d’utiliser Windows PowerShell pour créer le certificat, l’administrateur de l’autorité de certification doit créer et déployer un nouveau modèle qui prend en charge l’EKU sur le client.

## Pour envoyer une demande à une autorité de certification publique

1.  Ouvrez le fichier de sortie.

2.  Copiez et collez le contenu de la demande de signature de certificat (CSR).

3.  Si vous y êtes invité, spécifiez les éléments suivants :
    
      - **Microsoft** en tant que plateforme serveur.
    
      - **Services Internet (IIS)** en tant que version
    
      - **Serveur web** en tant que type d’utilisation.
    
      - **PKCS7** en tant que format de réponse.

4.  Une fois que l’autorité de certification publique a vérifié vos informations, vous recevez un message électronique contenant le texte requis pour votre certificat.

5.  Copiez le texte du message électronique et enregistrez-le dans un fichier texte (.txt) sur votre ordinateur local.

## Pour importer le certificat destiné à l’interface externe du serveur Edge

1.  Ouvrez une session en tant que membre du groupe Administrateurs sur le serveur Edge où vous avez créé la demande de certificat.

2.  Dans l’Assistant Déploiement, dans la page **Déployer un serveur Edge** , en regard de l’**Étape 3 : Demander, installer ou affecter les certificats** , cliquez sur **Réexécuter** .

3.  Dans la page **Tâches se rapportant aux certificats disponibles** , cliquez sur **Importer un certificat à partir d’un fichier .p7b, pfx ou .cer** .

4.  Dans la page **Importer un certificat** , cliquez sur **Parcourir** pour rechercher et sélectionner le certificat que vous avez demandé pour l’interface externe du serveur Edge (ou tapez le chemin complet et le nom du fichier). Si le certificat comprend une clé privée, sélectionnez **Le fichier du certificat contient la clé privée du certificat** et tapez le mot de passe de la clé privée. Cliquez sur **Suivant** .

5.  Dans la page **Importer le résumé du certificat** , passez en revue le certificat, puis cliquez sur **Suivant** .

6.  Dans **Exécution des commandes** , passez en revue les résultats de l’importation, cliquez sur **Afficher le journal** pour obtenir plus d’informations si nécessaire, puis cliquez sur **Terminer** pour terminer l’importation du certificat.

7.  Si vous configurez un pool de serveurs Edge, exportez le certificat avec sa clé privée, comme décrit à la section « Pour exporter le certificat avec la clé privée pour les serveurs Edge d’un pool » plus loin dans cet article. Copiez le certificat exporté sur les autres serveurs Edge, puis importez-le dans le magasin de l’ordinateur de chaque serveur Edge.

## Pour exporter le certificat avec la clé privée pour les serveurs Edge d’un pool

1.  Ouvrez une session en tant que membre du groupe Administrateurs sur le serveur Edge sur lequel vous avez importé le certificat.

2.  Cliquez sur **Démarrer** , sur **Exécuter** , puis tapez **MMC** .

3.  Dans la console MMC (Microsoft Management Console), cliquez sur **Fichier** , puis sur **Ajouter/supprimer un composant logiciel enfichable** .

4.  Dans **Ajouter ou supprimer des composants logiciels enfichables** , cliquez sur **Certificats** , puis sur **Ajouter** .

5.  Dans la boîte de dialogue **Certificats** , sélectionnez **Compte d’ordinateur** , cliquez sur **Suivant** , sélectionnez **L’ordinateur local (l’ordinateur sur lequel cette console s’exécute)** dans **Sélectionner l’ordinateur** , cliquez sur **Terminer** , puis enfin sur **OK** pour terminer la configuration de la console MMC (Microsoft Management Console).

6.  Double-cliquez sur **Certificats (ordinateur local)** pour développer les magasins de certificats, double-cliquez sur **Personnel** , puis sur **Certificats** .
    
    > [!IMPORTANT]  
    > Si aucun certificat ne se trouve dans le magasin personnel de certificats de l’ordinateur local, aucune clé privée n’est associée au certificat importé. Vérifiez la demande et la procédure d’importation. Si le problème persiste, contactez votre administrateur ou fournisseur d’autorités de certification.

7.  Dans **Magasin personnel de certificats pour l’ordinateur local** , cliquez avec le bouton droit sur le certificat que vous exportez, cliquez sur **Toutes les tâches** , puis sur **Exporter** .

8.  Dans l’Assistant Exportation du certificat, cliquez sur **Suivant** , sélectionnez **Oui, exporter la clé privée** , puis cliquez sur **Suivant** .
    
    > [!NOTE]  
    > Si la sélection <strong>Oui, exporter la clé privée</strong> n’est pas disponible, cela signifie que la clé privée associée au certificat n’était pas marquée pour l’exportation. Pour pouvoir poursuivre l’exportation, vous devrez faire une nouvelle demande de certificat en vous assurant que le certificat est marqué de façon à autoriser l’exportation de la clé privée. Contactez votre administrateur ou fournisseur d’autorités de certification.

9.  Dans la boîte de dialogue Exporter les formats de fichiers, sélectionnez **Échange d’informations personnelles – PKCS\#12 (.PFX)** , puis les éléments suivants :
    
      - Inclure tous les certificats dans le chemin d’accès de certification, si possible
    
      - Exporter toutes les propriétés étendues
        
        > [!WARNING]  
        > Lorsque vous exportez le certificat à partir d’un serveur Edge, ne sélectionnez pas <strong>Supprimer la clé privée si l’exportation s’est terminée correctement</strong> . Si vous sélectionnez cette option, vous serez obligé d’importer le certificat et la clé privée sur ce serveur Edge.

10. Cliquez sur **Suivant** .

11. Tapez un mot de passe pour la clé privée, tapez-le à nouveau pour confirmer votre entrée, puis cliquez sur **Suivant** .

12. Tapez un chemin d’accès et un nom de fichier avec l’extension .pfx pour le certificat exporté. Le chemin d’accès doit être accessible à tous les autres serveurs Edge du pool ou transportable au moyen d’un média amovible, comme par exemple, un disque mémoire flash USB. Cliquez sur **Suivant** .

13. Passez en revue le résumé dans **Fin de l’Assistant Exportation du certificat** , puis cliquez sur **Terminer** .

14. Dans la boîte de dialogue confirmant le succès de l’exportation, cliquez sur **OK**

15. Importez le fichier de certificat exporté vers les autres serveurs Edge en suivant les étapes décrites à la section « Pour importer le certificat destiné à l’interface externe du serveur Edge » plus haut dans cet article.

## Pour affecter le certificat destiné à l’interface externe du serveur Edge

1.  Sur chaque serveur Edge, dans l’Assistant Déploiement, à l’**Étape 3 : Demander, installer ou affecter les certificats** , cliquez sur **Réexécuter** .

2.  Dans la page **Tâches se rapportant aux certificats disponibles** , cliquez sur **Affecter un certificat existant** .

3.  Dans la page **Affectation du certificat** , cliquez sur **Certificat de serveur Edge externe** et activez la case à cocher **Utilisations de certificat avancées** .

4.  Dans la page **Utilisations de certificat avancées** , activez toutes les cases à cocher afin d’affecter le certificat pour toutes les utilisations.

5.  Dans la page **Magasin de certificats** , sélectionnez le certificat public que vous avez demandé et importé pour l’interface externe du serveur Edge.
    
    > [!NOTE]  
    > Si le certificat que vous avez demandé et importé ne se trouve pas dans la liste, l’une des méthodes d’identification et de résolution des problèmes consiste à vérifier que le nom du sujet et les autres noms du sujet du certificat respectent toutes les conditions requises pour le certificat et, si vous avez importé manuellement le certificat et la chaîne de certificats au lieu d’appliquer les procédures précédentes, contrôlez que le certificat se trouve dans le magasin de certificats correct (le magasin de certificats de l’ordinateur, et non le magasin de certificats de l’utilisateur ou du service).

6.  Dans la page **Résumé de l’affectation du certificat** , vérifiez vos paramètres, puis cliquez sur **Suivant** pour affecter les certificats.

7.  Dans la page de fin de l’Assistant, cliquez sur **Terminer** .

8.  Après avoir utilisé cette procédure pour affecter le certificat Edge, ouvrez le composant logiciel enfichable Certificats sur chaque serveur, développez **Certificats (ordinateur local)** , développez **Personnel** , cliquez sur **Certificats** , puis vérifiez dans le volet d’informations que le certificat figure bien dans la liste.

9.  Si votre déploiement inclut plusieurs serveurs Edge, répétez cette procédure pour chaque serveur Edge.

