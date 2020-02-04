---
title: 'Lync Server 2013 : Configuration des certificats pour l’interface interne Edge'
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
ms.openlocfilehash: ea6e462bdc629308493799c857ecb6b2434dc268
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732264"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-certificates-for-the-internal-edge-interface-in-lync-server-2013"></a>Configuration des certificats pour l’interface interne Edge dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-11-07_

<div>


> [!IMPORTANT]  
> Lorsque vous exécutez l’Assistant certificat, assurez-vous que vous êtes connecté à l’aide d’un compte associé à un compte qui dispose des autorisations appropriées pour le type de modèle de certificat que vous utilisez. Par défaut, une demande de certificat 2013 Lync Server utilise le modèle de certificat de serveur Web. Si vous utilisez un compte membre du groupe RTCUniversalServerAdmins pour demander un certificat à l’aide de ce modèle, vérifiez que le groupe a été affecté aux autorisations d’inscription requises pour utiliser ce modèle.



</div>

Un certificat unique est requis sur l’interface interne de chaque serveur Edge. Des certificats pour l’interface interne peuvent être émis par une autorité de certification d’entreprise interne ou une autorité de certification publique. Si votre organisation a déployé une autorité de certification interne, vous pouvez faire des économies sur les frais d’utilisation des certificats publics à l’aide de l’autorité de certification interne pour émettre le certificat de l’interface interne. Vous pouvez utiliser une autorité de certification Windows Server 2008 interne ou une autorité de certification Windows Server 2008 R2 pour créer ces certificats.

Pour plus d’informations sur ce problème et sur les autres exigences relatives aux certificats, voir [exigences relatives aux certificats pour l’accès des utilisateurs externes dans Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).

Pour configurer des certificats sur l’interface latérale interne d’un site, suivez les procédures décrites dans cette section pour effectuer les opérations suivantes :

1.  Téléchargez la chaîne de certification de l’autorité de certification pour l’interface interne vers chaque serveur Edge.

2.  Importez la chaîne de certification de l’autorité de certification pour l’interface interne sur chaque serveur Edge.

3.  Créez une demande de certificat pour l’interface interne, sur un serveur Edge, appelé le premier serveur Edge.

4.  Importez le certificat de l’interface interne sur le premier serveur de périphérie.

5.  Importez le certificat sur les autres serveurs Edge sur ce site (ou déployé sur ce dernier).

6.  Attribuez le certificat pour l’interface interne de chaque serveur Edge.

Si vous disposez de plusieurs sites avec des serveurs de frontière (autrement dit, une topologie de périmètre de plusieurs sites), ou des ensembles séparés de serveurs de frontière déployés dans des équilibreurs de charge différents, vous devez suivre ces étapes pour chaque site incluant des serveurs de périphérie et pour chaque ensemble de serveurs de périphérie. déploiement à l’arrière-plan d’un autre équilibreur de charge.

<div>


> [!NOTE]  
> Les étapes décrites dans cette section sont basées sur l’utilisation d’une autorité&nbsp;de certification windows Server 2008&nbsp;,&nbsp;d’une autorité de certification Windows Server 2008 R2, d’une autorité de certification Windows Server 2012 ou d’une autorité de certification Windows Server 2012 R2 pour créer un certificat pour chaque serveur Edge. Pour obtenir des instructions détaillées pour une autre autorité de certification, consultez la documentation de cette autorité de certification. Par défaut, tous les utilisateurs authentifiés disposent des droits d’utilisateur appropriés pour demander des certificats.<BR>Les procédures décrites dans cette section sont basées sur la création de demandes de certificat sur le serveur Edge dans le cadre du processus de déploiement de serveur Edge. Il est possible de créer des demandes de certificat à l’aide du serveur frontal. Vous pouvez le faire pour compléter la demande de certificat au début du processus de planification et de déploiement avant de commencer le déploiement des serveurs Edge. Pour cela, vous devez vous assurer que le certificat que vous demandez est défini à l’aide d’une clé privée exportable.<BR>Les procédures dans cette section décrivent l’utilisation d’un fichier. cer et d’un fichier. p7b pour le certificat. Si vous utilisez un autre type de fichier, modifiez ces procédures selon vos besoins.



</div>

<div>

## <a name="to-download-the-ca-certification-chain-for-the-internal-interface-using-certsrv-web-site"></a>Pour télécharger la chaîne de certification de l’autorité de certification pour l’interface interne à l’aide du site Web certsrv

1.  Connectez-vous à un serveur Lync Server 2013 dans le réseau interne (c’est-à-dire hors du serveur Edge) en tant que membre du groupe **administrateurs** .

2.  Exécutez la commande suivante à l’invite de commandes en cliquant sur **Démarrer**, puis en cliquant sur **exécuter**et en tapant ce qui suit :
    
        https://<name of your Issuing CA Server>/certsrv
    
    Par exemple :
    
        https://ca01.contoso.net/certsrv
    
    <div>
    

    > [!NOTE]  
    > Si vous utilisez une autorité de certification Windows Server 2008 ou Windows Server 2008 R2 entreprise, vous devez utiliser HTTPS, et non http.

    
    </div>

3.  Dans la page web certsrv de l’autorité de certification émettrice, sous **Sélectionnez une tâche**, cliquez sur **Télécharger un certificat d’autorité de certification, une chaîne de certificats ou la liste de révocation de certificats**.

4.  Sous **Télécharger un certificat d’autorité de certification, une chaîne de certificats ou une LRC**, cliquez sur **Télécharger la chaîne de certificats d’autorité**de certification.

5.  Dans la boîte de dialogue **téléchargement de fichier** , cliquez sur **Enregistrer**.

6.  Enregistrez le fichier. p7b sur le disque dur du serveur, puis copiez-le dans un dossier sur chaque serveur Edge.
    
    <div>
    

    > [!NOTE]  
    > Le fichier. p7b contient tous les certificats figurant dans le chemin de certification. Pour afficher le chemin d’accès de certification, ouvrez le certificat de serveur, puis cliquez sur le chemin d’accès de certification.

    
    </div>

</div>

<div>

## <a name="to-export-the-ca-certification-chain-for-the-internal-interface-using-mmc"></a>Pour exporter la chaîne de certification de l’autorité de certification pour l’interface interne à l’aide de MMC

1.  Vous pouvez exporter le certificat racine de l’autorité de certification à partir de n’importe quel ordinateur sur lequel est connecté le domaine à l’aide de Microsoft Management Console (MMC). Cliquez sur **Démarrer**, sur **exécuter**, puis tapez **MMC**.

2.  Dans la console MMC, cliquez sur **fichier**, puis sur **Ajouter/supprimer**.

3.  Dans la liste de la boîte de dialogue **Ajouter ou supprimer des composants additionnels** , sélectionnez **certificats**, puis cliquez sur **Ajouter**. Lorsque vous y êtes invité, sélectionnez **compte d’ordinateur**. Dans la boîte de dialogue **Sélectionner un ordinateur**, sélectionnez **Ordinateur local**. Cliquez sur **Terminer**. Cliquez sur **OK**.

4.  Développez **certificats (ordinateur local)**. Développez **autorités de certification racine de confiance**, puis sélectionnez **certificats**.

5.  Cliquez sur le certificat racine émis par votre autorité de certification. Cliquez avec le bouton droit sur le certificat, sélectionnez **toutes les tâches**, sélectionnez **Exporter**. L' **Assistant exportation de certificat** s’ouvre.

6.  Dans l’**Assistant Exportation du certificat**, cliquez sur **Suivant**.

7.  Dans la boîte de dialogue **Exporter le format de fichier** , sélectionnez le format d’exportation. Nous vous recommandons d’utiliser la **syntaxe de message \#cryptographique standard-certificats PKCS 7 (. P7B)**. Si vous sélectionnez la **syntaxe de message cryptographique standard- \#certificats PKCS 7 (. P7B)**, activez la case à cocher **inclure tous les certificats dans le chemin de certification si possible** pour exporter la chaîne de certificats, y compris le certificat de l’autorité de certification racine et les certificats d’autorité de certification intermédiaires. Cliquez sur **Suivant**.

8.  Dans la boîte de dialogue **fichier à exporter** du nom de fichier, tapez le chemin d’accès et le nom du fichier (l’extension par défaut est. p7b) du certificat exporté. Vous pouvez également cliquer sur **Parcourir**, recherchez le répertoire dans lequel placer le certificat exporté et attribuez un nom au certificat exporté. Cliquez sur **Enregistrer**. Cliquez sur **Suivant**.

9.  Examinez le résumé des actions, puis cliquez sur **Terminer** pour terminer l’exportation du certificat. Cliquez sur **OK** pour confirmer l’exportation.

</div>

<div>

## <a name="to-import-the-ca-certification-chain-for-the-internal-interface"></a>Pour importer la chaîne de certification de l’autorité de certification pour l’interface interne

1.  Sur chaque serveur Edge, ouvrez Microsoft Management Console (MMC) en cliquant sur **Démarrer**, sur **exécuter**, en tapant **MMC** dans la zone **ouvrir** , puis en cliquant sur **OK**.

2.  Dans le menu **fichier** , cliquez sur **Ajouter/supprimer un composant logiciel enfichable**, puis cliquez sur **Ajouter**.

3.  Dans la boîte de dialogue **Ajouter des composants logiciels enfichables autonomes** , cliquez sur **certificats**, puis cliquez sur **Ajouter**.

4.  Dans la boîte de dialogue **Composant logiciel enfichable Certificats**, cliquez sur **Compte d’ordinateur**, puis sur **Suivant**.

5.  Dans la boîte de dialogue **Sélectionner un ordinateur** , assurez-vous que l' **ordinateur local (sur lequel cette console s’exécute)** est sélectionné, puis cliquez sur **Terminer**.

6.  Cliquez sur **Fermer**, puis cliquez sur **OK**.

7.  Dans l’arborescence de la console, développez **certificats (ordinateur local)**, cliquez avec le bouton droit sur **autorités de certification racine de confiance**, pointez sur **toutes les tâches**, puis cliquez sur **Importer**.

8.  Dans l’Assistant, dans **fichier à importer**, spécifiez le nom de fichier du certificat (autrement dit, le nom de l’interface que vous avez spécifiée lors du téléchargement de la chaîne de certification de l’autorité de certification pour l’interface interne au cours de la procédure précédente).

9.  Répétez cette procédure sur chaque serveur Edge.

</div>

<div>

## <a name="to-create-the-certificate-request-for-the-internal-interface"></a>Pour créer une demande de certificat pour l’interface interne

1.  Sur l’un des serveurs Edge, démarrez l’Assistant Déploiement, puis, en regard de l' **étape 3 : demandez, installez ou attribuez des certificats**, cliquez sur **exécuter**.
    
    <div>
    

    > [!NOTE]  
    > Si vous avez plusieurs serveurs Edge à un emplacement dans un pool, vous pouvez exécuter l’Assistant certificat sur n’importe quel serveur Edge.<BR>Après avoir exécuté l’étape 3 pour la première fois, le bouton est modifié pour <STRONG>s’exécuter de nouveau</STRONG>et une coche verte indiquant la réussite de la tâche n’est pas affichée tant que tous les certificats requis n’ont pas été demandés, installés et attribués.

    
    </div>

2.  Dans la page **Tâches se rapportant aux certificats disponibles**, cliquez sur **Créer une demande de certificat**.

3.  Dans la page **demande de certificat** , cliquez sur **suivant**.

4.  Dans la page **Demandes différées ou immédiates**, cliquez sur **Préparer la demande, mais ne pas l’envoyer maintenant**.

5.  Dans la page **fichier de demande de certificat** , tapez le chemin d’accès complet et le nom du fichier vers lequel vous voulez enregistrer la requête (par exemple, **c :\\CERT\_Internal\_Edge. cer**).

6.  Dans la page **spécifier un modèle de certificat secondaire** , pour utiliser un modèle autre que le modèle par défaut du serveur Web, activez la case à cocher utiliser un autre **modèle de certificat pour l’autorité de certification sélectionnée** .

7.  Dans la page **paramètres de nom et de sécurité** , procédez comme suit :
    
      - Dans **nom convivial**, tapez un nom d’affichage pour le certificat (par exemple, bord interne).
    
      - En **longueur**, spécifiez la longueur en bits (en général, la valeur par défaut **2048**).
        
        <div>
        

        > [!NOTE]  
        > Des longueurs de bits plus élevées offrent une plus grande sécurité, mais ils ont un impact négatif sur la vitesse.

        
        </div>
    
      - Si le certificat doit être exportable, activez la case à cocher **marquer le certificat comme étant exportable** .

8.  Dans la page informations sur l' **organisation** , tapez le nom de l’organisation et l’unité d’organisation (UO) (par exemple, une division ou un service).

9.  Dans la page **informations géographiques** , spécifiez les informations d’emplacement.

10. Sur la page nom de l’objet **/nom** de l’objet, les informations à remplir automatiquement par l’Assistant sont affichées.

11. Dans la page **configurez** d’autres noms d’objet, spécifiez d’autres noms d’objet obligatoires.

12. Dans la page Résumé de la **demande** , passez en revue les informations de certificats qui vont être utilisées pour générer la requête.

13. Une fois les commandes terminées, procédez comme suit :
    
      - Pour afficher le journal de la demande de certificat, cliquez sur **afficher le journal**.
    
      - Pour remplir la demande de certificat, cliquez sur **suivant**.

14. Dans la page **fichier de demande de certificat** , procédez comme suit :
    
      - Pour afficher le fichier de demande de signature de certificat généré (CSR), cliquez sur **Afficher**.
    
      - Pour fermer l’Assistant, cliquez sur **Terminer**.

15. Envoyez ce fichier à votre autorité de certification (par courrier électronique ou autre méthode prise en charge par votre organisation) et, lorsque vous recevez le fichier de réponse, copiez le nouveau certificat sur cet ordinateur pour qu’il soit disponible à des fins d’importation.

</div>

<div>

## <a name="to-import-the-certificate-for-the-internal-interface"></a>Pour importer le certificat de l’interface interne

1.  Ouvrez une session sur le serveur Edge sur lequel vous avez créé la demande de certificat en tant que membre du groupe administrateurs locaux.

2.  Dans l’Assistant Déploiement, en regard de l' **étape 3 : demandez, installez ou attribuez des certificats**, cliquez de **nouveau sur exécuter**.
    
    Après avoir exécuté l’étape 3 pour la première fois, le bouton est modifié pour **s’exécuter de nouveau**, mais une coche verte (indiquant la réussite de la tâche) ne s’affiche pas tant que tous les certificats requis n’ont pas été demandés, installés et attribués.

3.  Dans la page **tâches de certification disponibles** , cliquez sur **Importer un certificat à partir de a. Le fichier P7B,. pfx ou. cer**.

4.  Sur la page **importer le certificat** , tapez le chemin d’accès complet et le nom de fichier du certificat que vous avez demandé et reçu pour l’interface interne du serveur Edge (ou cliquez sur **Parcourir** pour rechercher et sélectionner le fichier).

5.  Si vous importez des certificats pour les autres membres du pool ayant un certificat contenant une clé privée, activez la case à cocher le **fichier de certificat contient la clé privée du** certificat et spécifiez le mot de passe.

</div>

<div>

## <a name="to-export-the-certificate-with-the-private-key-for-edge-servers-in-a-pool"></a>Pour exporter le certificat avec la clé privée pour les serveurs Edge dans un pool

1.  Ouvrez une session en tant que membre du groupe Administrateurs sur le serveur Edge sur lequel vous avez importé le certificat.

2.  Cliquez sur **Démarrer**, sur **exécuter**, puis tapez **MMC**.

3.  Dans la console MMC, cliquez sur **fichier**, puis sur **Ajouter/supprimer un composant logiciel enfichable**.

4.  Dans la page Ajouter ou supprimer des composants logiciels enfichables, cliquez sur **certificats**, puis sur **Ajouter**.

5.  Dans la boîte de dialogue composant logiciel enfichable Certificats, sélectionnez **compte d’ordinateur**. Cliquez sur **Suivant**. Sur votre ordinateur, sélectionnez **ordinateur local : (l’ordinateur sur lequel cette console s’exécute)**. Cliquez sur **Terminer**. Cliquez sur **OK** pour terminer la configuration de la console MMC.

6.  Double-cliquez sur **Certificats (ordinateur local)** pour développer les magasins de certificats. Double-cliquez sur **personnel**, puis double-cliquez sur **certificats**.
    
    <div>
    

    > [!IMPORTANT]  
    > S’il n’y a aucun certificat dans le magasin personnel de certificats de l’ordinateur local, il n’existe aucune clé privée associée au certificat importé. Passez en revue les étapes de demande et d’importation. Si le problème persiste, contactez votre administrateur ou fournisseur de l’autorité de certification.

    
    </div>

7.  Dans le magasin personnel de certificats de l’ordinateur local, cliquez avec le bouton droit sur le certificat que vous exportez. Cliquez sur **toutes les tâches**, puis sur **Exporter**.

8.  Dans l’Assistant exportation de certificat, cliquez sur **suivant**. Sélectionnez **Oui, exporter la clé privée**. Cliquez sur **Suivant**.
    
    <div>
    

    > [!NOTE]  
    > Si la sélection est <STRONG>Oui, exporter la clé privée</STRONG> n’est pas disponible, la clé privée associée à ce certificat n’est pas marquée pour l’exportation. Vous devez demander à nouveau le certificat, en veillant à ce que le certificat soit marqué pour autoriser l’exportation de la clé privée avant de poursuivre l’exportation. Contactez votre administrateur ou fournisseur de l’autorité de certification.

    
    </div>

9.  Dans la boîte de dialogue Exporter les formats de fichier, sélectionnez **échange\#d’informations personnelles – PKCS 12 (. PFX)** , puis sélectionnez les options suivantes :
    
      - Incluez tous les certificats dans le chemin de certification, le cas échéant.
    
      - Exporter toutes les propriétés étendues
        
        <div>
        

        > [!WARNING]  
        > Lorsque vous exportez le certificat à partir d’un serveur Edge, ne sélectionnez pas <STRONG>Supprimer la clé privée si l’exportation est réussie</STRONG>. La sélection de cette option nécessite l’importation du certificat et de la clé privée vers ce serveur Edge.

        
        </div>
    
    Cliquez sur **Suivant** pour continuer.

10. Si vous voulez affecter un mot de passe pour protéger la clé privée, tapez un mot de passe pour la clé privée. Entrez à nouveau le mot de passe pour le confirmer. Cliquez sur **Suivant**.

11. Tapez un chemin d’accès et un nom de fichier avec l’extension .pfx pour le certificat exporté. Le chemin d’accès doit être accessible à tous les autres serveurs de périphérie du pool ou disponible pour le transport par le biais de médias amovibles (par exemple, un lecteur flash USB). Cliquez sur **Suivant**.

12. Passez en revue le résumé de la boîte de dialogue de l’Assistant d’exportation de certificat. Cliquez sur **Terminer**.

13. Cliquez sur **OK** dans la boîte de dialogue indiquant que l’exportation a abouti.

14. Importez le fichier de certificat exporté vers les autres serveurs Edge en suivant les étapes décrites dans la rubrique [configurer des certificats pour les procédures Lync Server 2013](lync-server-2013-set-up-certificates-for-the-external-edge-interface.md) .

</div>

<div>

## <a name="to-assign-the-internal-certificate-on-the-edge-servers"></a>Pour affecter le certificat interne sur les serveurs de périphérie

1.  Sur chaque serveur Edge, dans l’Assistant Déploiement, en regard de l' **étape 3 : demandez, installez ou attribuez des certificats**, cliquez de **nouveau sur exécuter**.

2.  Dans la page **tâches de certification disponibles** , cliquez sur **attribuer un certificat existant**.

3.  Dans la page **Affectation de certificat**, sélectionnez **Serveur Edge interne** dans la liste.

4.  Dans la page **magasin de certificats** , sélectionnez le certificat que vous avez importé pour le bord interne (à partir de la procédure précédente).

5.  Dans la page **Résumé des affectations de certificat** , passez en revue vos paramètres, puis cliquez sur **suivant** pour attribuer les certificats.

6.  Dans la page de fin de l’Assistant, cliquez sur **Terminer**.

7.  Lorsque vous utilisez cette procédure pour attribuer le certificat de bord interne, ouvrez le composant logiciel enfichable Certificats sur chaque serveur, développez **certificats (ordinateur local)**, développez **personnel**, cliquez sur **certificats**, puis vérifiez dans le volet d’informations que le certificat de bord interne est répertorié.

8.  Si votre déploiement inclut plusieurs serveurs Edge, répétez cette procédure pour chaque serveur Edge.

</div>

</div>

<span> </span>

</div>

</div>

</div>

