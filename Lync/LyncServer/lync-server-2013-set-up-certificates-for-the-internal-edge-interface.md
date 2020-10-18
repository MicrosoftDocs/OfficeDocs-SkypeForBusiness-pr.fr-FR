---
title: 'Lync Server 2013 : configuration des certificats pour l’interface Edge interne'
description: 'Lync Server 2013 : configurez les certificats pour l’interface Edge interne.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up certificates for the internal edge interface
ms:assetid: a1963cc9-87c5-4935-86c0-6bedc6afd0ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412750(v=OCS.15)
ms:contentKeyID: 48184949
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52473069735d4f48c247367194139c479e71293f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575400"
---
# <a name="set-up-certificates-for-the-internal-edge-interface-in-lync-server-2013"></a>Configurer des certificats pour l’interface Edge interne dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-11-07_

<div>


> [!IMPORTANT]  
> Lorsque vous exécutez l’Assistant Certificat, veillez à être connecté avec un compte membre d’un groupe auquel les autorisations appropriées ont été octroyées pour le type de modèle de certificat que vous allez utiliser. Par défaut, une demande de certificat Lync Server 2013 utilisera le modèle de certificat de serveur Web. Si vous utilisez un compte membre du groupe RTCUniversalServerAdmins pour demander un certificat qui utilise ce modèle, vérifiez que le groupe possède les autorisations d’inscription requises pour utiliser ce modèle.



</div>

Un certificat unique est requis sur l’interface interne de chaque serveur Edge. Les certificats pour l’interface interne peuvent être émis par une autorité de certification d’entreprise interne ou une autorité de certification publique. Si votre organisation a déployé une autorité de certification interne, vous pouvez épargner sur les frais d’utilisation des certificats publics à l’aide de l’autorité de certification interne pour émettre le certificat pour l’interface interne. Vous pouvez utiliser une autorité de certification Windows Server 2008 ou Windows Server 2008 R2 interne pour créer ces certificats.

Pour plus d’informations à ce sujet et sur d’autres exigences de certificat, voir [Certificate Requirements for External User Access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).

Pour configurer des certificats sur l’interface Edge interne au niveau d’un site, utilisez les procédures de cette section pour effectuer les opérations suivantes :

1.  Téléchargez la chaîne de certification de l’autorité de certification pour l’interface interne sur chaque serveur Edge.

2.  Importez la chaîne de certification de l’autorité de certification pour l’interface interne sur chaque serveur Edge.

3.  Créez la demande de certificat pour l’interface interne, sur un serveur Edge, appelé le premier serveur Edge.

4.  Importez le certificat pour l’interface interne sur le premier serveur Edge.

5.  Importez le certificat sur les autres serveurs Edge de ce site (ou déployé derrière cet équilibrage de charge).

6.  Assignez le certificat pour l’interface interne de chaque serveur Edge.

Si vous avez plusieurs sites avec des serveurs Edge (autrement dit, une topologie Edge sur plusieurs sites) ou des ensembles de serveurs Edge séparés déployés derrière différents programmes d’équilibrage de la charge, vous devez suivre ces étapes pour chaque site doté de serveurs Edge et pour chaque ensemble de serveurs Edge déployé derrière un programme d’équilibrage de charge différent.

<div>


> [!NOTE]  
> Les étapes des procédures décrites dans cette section sont basées sur l’utilisation d’une autorité de certification Windows Server &nbsp; 2008, Windows server &nbsp; 2008 &nbsp; R2 ca, Windows Server 2012 ca ou Windows Server 2012 R2 pour créer un certificat pour chaque serveur Edge. Pour obtenir des instructions détaillées pour toute autre autorité de certification, consultez la documentation de cette autorité de certification. Par défaut, tous les utilisateurs authentifiés disposent des droits d’utilisateur appropriés pour demander des certificats.<BR>Les procédures de cette section sont basées sur la création de demandes de certificats sur le serveur Edge dans le cadre du processus de déploiement du serveur Edge. Il est possible de créer des demandes de certificat à l’aide du serveur frontal. Vous pouvez effectuer cette opération pour terminer la demande de certificat au début du processus de planification et de déploiement, avant de commencer le déploiement des serveurs Edge. Pour ce faire, vous devez vous assurer que le certificat que vous demandez est défini avec une clé privée exportable.<BR>Les procédures décrites dans cette section décrivent l’utilisation d’un fichier. cer et d’un fichier. p7b pour le certificat. Si vous utilisez un autre type de fichier, modifiez ces procédures selon vos besoins.



</div>

<div>

## <a name="to-download-the-ca-certification-chain-for-the-internal-interface-using-certsrv-web-site"></a>Pour télécharger la chaîne de certification de l’autorité de certification pour l’interface interne à l’aide du site Web certsrv

1.  Connectez-vous à un serveur Lync Server 2013 sur le réseau interne (c’est-à-dire, pas au serveur Edge) en tant que membre du groupe **administrateurs** .

2.  À l’invite de commandes, exécutez la commande suivante en cliquant sur **Démarrer**, sur **exécuter**, puis en tapant ce qui suit :
    
        https://<name of your Issuing CA Server>/certsrv
    
    Par exemple :
    
        https://ca01.contoso.net/certsrv
    
    <div>
    

    > [!NOTE]  
    > Si vous utilisez une autorité de certification Windows Server 2008 ou Windows Server 2008 R2 Enterprise, vous devez utiliser le protocole HTTPS, et non http.

    
    </div>

3.  Sur la page Web certsrv de l’autorité de certification émettrice, sous **Sélectionner une tâche**, cliquez sur **Télécharger un certificat d’autorité de certification, une chaîne de certificats ou une liste de révocation de**certificats.

4.  Sous **Télécharger un certificat d’autorité de certification, une chaîne de certificats ou une liste de révocation de**certificats, cliquez sur **Télécharger la chaîne de certificat ca**.

5.  Dans la boîte de dialogue **Téléchargement de fichiers**, cliquez sur **Enregistrer**.

6.  Enregistrez le fichier. p7b sur le disque dur du serveur, puis copiez-le dans un dossier sur chaque serveur Edge.
    
    <div>
    

    > [!NOTE]  
    > Le fichier. p7b contient tous les certificats qui se trouvent dans le chemin d’accès de certification. Pour afficher le chemin d’accès de certification, ouvrez le certificat de serveur et cliquez sur le chemin d’accès de certification.

    
    </div>

</div>

<div>

## <a name="to-export-the-ca-certification-chain-for-the-internal-interface-using-mmc"></a>Pour exporter la chaîne de certification de l’autorité de certification pour l’interface interne à l’aide de MMC

1.  Vous pouvez exporter le certificat racine de l’autorité de certification à partir d’un ordinateur appartenant à un domaine à l’aide de la console MMC (Microsoft Management Console). Cliquez sur **Démarrer**, sur **exécuter**, puis tapez **MMC**.

2.  Dans la console MMC, cliquez sur **fichier**, puis sur **Ajouter/supprimer**.

3.  Dans la liste de la boîte de dialogue **Ajouter ou supprimer des composants logiciels enfichables** , sélectionnez **certificats**, puis cliquez sur **Ajouter**. Lorsque vous y êtes invité, sélectionnez **compte d’ordinateur**. Dans la boîte de dialogue **Sélectionner un ordinateur** , sélectionnez **ordinateur local**. Cliquez sur **Terminer**. Cliquez sur **OK**.

4.  Développez **certificats (ordinateur local)**. Développez **autorités de certification racines de confiance**, puis sélectionnez **certificats**.

5.  Cliquez sur le certificat racine émis par votre autorité de certification. Cliquez avec le bouton droit sur le certificat, sélectionnez **toutes les tâches**, sélectionnez **Exporter**. L' **Assistant exportation de certificat** s’ouvre.

6.  Dans l’**Assistant Exportation de certificat**, cliquez sur **Suivant**.

7.  Dans la boîte de dialogue **Exporter le format de fichier** , sélectionnez un format d’exportation. Nous vous recommandons d’utiliser la **syntaxe de message de chiffrement standard – \# certificats PKCS 7 (. P7B)**. Si vous sélectionnez la **syntaxe de message chiffré standard – \# certificats PKCS 7 (. P7B)**, activez la case à cocher **inclure tous les certificats dans le chemin d’accès de certification si possible** pour exporter la chaîne de certificats, y compris le certificat de l’autorité de certification racine et les certificats de l’autorité de certification intermédiaire. Cliquez sur **Suivant**.

8.  Dans la boîte de dialogue **fichier à exporter** de l’entrée nom de fichier, tapez un chemin d’accès et un nom de fichier (extension. p7b) pour le certificat exporté. Éventuellement, cliquez sur **Parcourir**, recherchez un répertoire dans lequel placer le certificat exporté et attribuez un nom au certificat exporté. Cliquez sur **Enregistrer**. Cliquez sur **Suivant**.

9.  Examinez le résumé des actions, puis cliquez sur **Terminer** pour terminer l’exportation du certificat. Cliquez sur **OK** pour confirmer l’exportation.

</div>

<div>

## <a name="to-import-the-ca-certification-chain-for-the-internal-interface"></a>Pour importer la chaîne de certification de l’autorité de certification pour l’interface interne

1.  Sur chaque serveur Edge, ouvrez la console MMC (Microsoft Management Console) en cliquant sur **Démarrer**, puis sur **exécuter**, en tapant **MMC** dans la zone **ouvrir** , puis en cliquant sur **OK**.

2.  Dans le menu **Fichier**, cliquez sur **Ajouter/Supprimer un composant logiciel enfichable**, puis sur **Ajouter**.

3.  Dans la zone **Ajout d’un composant logiciel enfichable autonome**, cliquez sur **Certificats**, puis sur **Ajouter**.

4.  Dans la boîte de dialogue **Composant logiciel enfichable Certificats**, cliquez sur **Compte d’ordinateur**, puis sur **Suivant**.

5.  Dans la boîte de dialogue **Sélectionner un ordinateur**, assurez-vous que la case à cocher **Ordinateur local : (l’ordinateur sur lequel cette console s’exécute)** est activée, puis cliquez sur **Terminer**.

6.  Cliquez sur **Fermer**, puis sur **OK**.

7.  Dans l’arborescence de la console, développez **certificats (ordinateur local)**, cliquez avec le bouton droit sur **autorités de certification racines de confiance**, pointez sur **toutes les tâches**, puis cliquez sur **Importer**.

8.  Dans l’Assistant, dans **fichier à importer**, spécifiez le nom de fichier du certificat (autrement dit, le nom de celui que vous avez spécifié lorsque vous avez téléchargé la chaîne de certification de l’autorité de certification pour l’interface interne dans la procédure précédente).

9.  Répétez cette procédure sur chaque serveur Edge.

</div>

<div>

## <a name="to-create-the-certificate-request-for-the-internal-interface"></a>Pour créer la demande de certificat pour l’interface interne

1.  Sur l’un des serveurs Edge, démarrez l’Assistant Déploiement et en regard de l' **étape 3 : demander, installer ou assigner les certificats**, cliquez sur **exécuter**.
    
    <div>
    

    > [!NOTE]  
    > Si vous disposez de plusieurs serveurs Edge dans un même emplacement d’un pool, vous pouvez exécuter l’Assistant certificat sur l’un des serveurs Edge.<BR>Après avoir exécuté l’étape 3 pour la première fois, le bouton passe à <STRONG>réexécuter</STRONG>, et une coche verte indiquant que l’exécution de la tâche a réussi s’affiche jusqu’à ce que tous les certificats requis aient été demandés, installés et affectés.

    
    </div>

2.  Dans la page **Tâches se rapportant aux certificats disponibles**, cliquez sur **Créer une demande de certificat**.

3.  Dans la page **Demande de certificat**, cliquez sur **Suivant**.

4.  Sur la page **demandes différées ou immédiates** , cliquez sur **préparer la demande maintenant, mais l’envoyer plus tard**.

5.  Dans la page **fichier de demande de certificat** , tapez le chemin d’accès complet et le nom du fichier dans lequel la demande doit être enregistrée (par exemple, **c : \\ CERT \_ Internal \_ Edge. cer**).

6.  Sur la page **spécifier un autre modèle de certificat** , pour utiliser un autre modèle que le modèle serveur Web par défaut, activez la case à cocher utiliser un autre modèle **de certificat pour l’autorité de certification sélectionnée** .

7.  Dans la page **Nom et paramètres de sécurité**, procédez comme suit :
    
      - Dans **nom convivial**, tapez un nom d’affichage pour le certificat (par exemple, Edge interne).
    
      - Dans **longueur en bits**, spécifiez la longueur en bits (généralement, la valeur par défaut de **2048**).
        
        <div>
        

        > [!NOTE]  
        > Les longueurs de bits plus élevées offrent davantage de sécurité, mais ont un impact négatif sur la vitesse.

        
        </div>
    
      - Si le certificat doit être exportable, activez la case à cocher **marquer la clé privée du certificat comme exportable** .

8.  Sur la page informations sur l' **organisation** , tapez le nom de l’organisation et de l’unité d’organisation (ou) (par exemple, une division ou un service).

9.  Dans la page **Informations géographiques**, spécifiez les informations d’emplacement.

10. Dans la page **Nom du sujet/Autres noms du sujet**, le système affiche les informations automatiquement renseignées par l’Assistant.

11. Dans la page **Configurer d’autres noms du sujet supplémentaires** , spécifiez les autres noms du sujet supplémentaires nécessaires.

12. Sur la page Résumé de la **demande** , passez en revue les informations de certificat qui vont être utilisées pour générer la demande.

13. Une fois les commandes terminées, procédez comme suit :
    
      - Pour afficher le journal de la demande de certificat, cliquez sur **afficher le journal**.
    
      - Pour terminer la demande de certificat, cliquez sur **suivant**.

14. Dans la page **fichier de demande de certificat** , procédez comme suit :
    
      - Pour afficher le fichier de demande de signature de certificat (CSR) généré, cliquez sur **Afficher**.
    
      - Pour fermer l’Assistant, cliquez sur **Terminer**.

15. Envoyez ce fichier à votre autorité de certification (par courrier électronique ou une autre méthode prise en charge par votre organisation pour votre autorité de certification d’entreprise) et, lorsque vous recevez le fichier de réponse, copiez le nouveau certificat sur cet ordinateur pour qu’il soit disponible pour l’importation.

</div>

<div>

## <a name="to-import-the-certificate-for-the-internal-interface"></a>Pour importer le certificat pour l’interface interne

1.  Ouvrez une session sur le serveur Edge sur lequel vous avez créé la demande de certificat en tant que membre du groupe Administrateurs local.

2.  Dans l’Assistant Déploiement, en regard de **étape 3 : demander, installer ou assigner les certificats**, cliquez sur **réexécuter**.
    
    Après avoir exécuté l’étape 3 pour la première fois, le bouton passe à **réexécuter**, mais une coche verte (indiquant l’exécution réussie de la tâche) ne s’affiche qu’une fois que tous les certificats requis ont été demandés, installés et affectés.

3.  Sur la page **tâches de certificats disponibles** , cliquez sur **Importer un certificat à partir d’un. Fichier P7B,. pfx ou. cer**.

4.  Sur la page **Importer un certificat** , tapez le chemin d’accès complet et le nom de fichier du certificat que vous avez demandé et reçu pour l’interface interne de ce serveur Edge (ou cliquez sur **Parcourir** pour rechercher et sélectionner le fichier).

5.  Si vous importez des certificats pour d’autres membres du pool, un certificat contenant une clé privée, activez la case à cocher le **fichier de certificat contient la clé privée du** certificat et spécifiez le mot de passe.

</div>

<div>

## <a name="to-export-the-certificate-with-the-private-key-for-edge-servers-in-a-pool"></a>Pour exporter le certificat avec la clé privée pour les serveurs Edge dans un pool

1.  Ouvrez une session en tant que membre du groupe Administrateurs sur le serveur Edge sur lequel vous avez importé le certificat.

2.  Cliquez sur **Démarrer**, sur **exécuter**, puis tapez **MMC**.

3.  Dans la console MMC, cliquez sur **fichier**, puis sur **Ajouter/supprimer un composant logiciel enfichable**.

4.  Dans la page Ajouter ou supprimer des composants logiciels enfichables, cliquez sur **certificats**, puis sur **Ajouter**.

5.  Dans la boîte de dialogue composant logiciel enfichable Certificats, sélectionnez **compte d’ordinateur**. Cliquez sur **Suivant**. Dans sélectionner un ordinateur, sélectionnez **ordinateur local : (l’ordinateur sur lequel cette console est exécutée)**. Cliquez sur **Terminer**. Cliquez sur **OK** pour terminer la configuration de la console MMC.

6.  Double-cliquez sur **certificats (ordinateur local)** pour développer les magasins de certificats. Double-cliquez sur **personnel**, puis sur **certificats**.
    
    <div>
    

    > [!IMPORTANT]  
    > S’il n’y a aucun certificat dans le magasin personnel de certificats pour l’ordinateur local, il n’y a pas de clé privée associée au certificat importé. Passez en revue les étapes de demande et d’importation. Si le problème persiste, contactez l’administrateur de votre autorité de certification ou votre fournisseur.

    
    </div>

7.  Dans le magasin personnel de certificats de l’ordinateur local, cliquez avec le bouton droit sur le certificat que vous exportez. Cliquez sur **toutes les tâches**, puis sur **Exporter**.

8.  Dans l’Assistant exportation de certificat, cliquez sur **suivant**. Sélectionnez **Oui, exporter la clé privée**. Cliquez sur **Suivant**.
    
    <div>
    

    > [!NOTE]  
    > Si la sélection est <STRONG>Oui, l’exportation de la clé privée</STRONG> n’est pas disponible, la clé privée associée à ce certificat n’a pas été marquée pour l’exportation. Vous devrez demander de nouveau le certificat, en vous assurant que le certificat est marqué pour autoriser l’exportation de la clé privée avant de pouvoir poursuivre l’exportation. Contactez l’administrateur ou le fournisseur de votre autorité de certification.

    
    </div>

9.  Dans la boîte de dialogue Exporter les formats de fichiers, sélectionnez **échange d’informations personnelles – PKCS \# 12 (. PFX)** , puis sélectionnez ce qui suit :
    
      - Inclure tous les certificats dans le chemin d’accès de certification si possible
    
      - Exporter toutes les propriétés étendues
        
        <div>
        

        > [!WARNING]  
        > Lorsque vous exportez le certificat à partir d’un serveur Edge, ne sélectionnez pas <STRONG>Supprimer la clé privée si l’exportation réussit</STRONG>. Si vous sélectionnez cette option, vous devez importer le certificat et la clé privée sur ce serveur Edge.

        
        </div>
    
    Cliquez sur **Suivant** pour continuer.

10. Si vous souhaitez affecter un mot de passe pour protéger la clé privée, tapez un mot de passe pour la clé privée. Entrez à nouveau le mot de passe pour le confirmer. Cliquez sur **Suivant**.

11. Tapez un chemin d’accès et un nom de fichier pour le certificat exporté, à l’aide d’une extension de fichier. pfx. Le chemin d’accès doit être accessible à tous les autres serveurs Edge du pool ou être disponible pour le transport via un support amovible (par exemple, un lecteur flash USB). Cliquez sur **Suivant**.

12. Consultez le résumé dans la boîte de dialogue fin de l’Assistant Exportation du certificat. Cliquez sur **Terminer**.

13. Cliquez sur **OK** dans la boîte de dialogue d’exportation réussie.

14. Importez le fichier de certificat exporté vers les autres serveurs Edge en suivant les étapes décrites dans les procédures [set up Certificates for the external Edge interface for Lync Server 2013](lync-server-2013-set-up-certificates-for-the-external-edge-interface.md) .

</div>

<div>

## <a name="to-assign-the-internal-certificate-on-the-edge-servers"></a>Pour affecter le certificat interne sur les serveurs Edge

1.  Sur chaque serveur Edge, dans l’Assistant Déploiement, à côté de **étape 3 : demander, installer ou assigner les certificats**, cliquez sur **réexécuter**.

2.  Dans la page **tâches de certificats disponibles** , cliquez sur **affecter un certificat existant**.

3.  Sur la page **affectation de certificat** , sélectionnez serveur **Edge interne** dans la liste.

4.  Sur la page **magasin de certificats** , sélectionnez le certificat que vous avez importé pour le serveur Edge interne (à partir de la procédure précédente).

5.  Sur la page Résumé de l' **affectation du certificat** , vérifiez vos paramètres, puis cliquez sur **suivant** pour affecter les certificats.

6.  Dans la page de fin de l’Assistant, cliquez sur **Terminer**.

7.  Après avoir utilisé cette procédure pour affecter le certificat Edge interne, ouvrez le composant logiciel enfichable certificat sur chaque serveur, développez **certificats (ordinateur local)**, développez **personnel**, cliquez sur **certificats**, puis vérifiez dans le volet d’informations que le certificat de périmètre interne est affiché.

8.  Si votre déploiement comprend plusieurs serveurs Edge, répétez cette procédure pour chaque serveur Edge.

</div>

</div>

<span> </span>

</div>

</div>

</div>

