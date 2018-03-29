---
title: Déploiement des serveurs Edge dans Skype Entreprise Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Hybrid
ms.assetid: 63c7251c-080a-4175-99a6-f86d0266d6bc
description: 'Résumé : Apprenez à déployer des serveurs de périphérie dans votre Skype pour environnement d’entreprise serveur 2015.'
ms.openlocfilehash: ec69655ad5a614e9a2a22e82b7c1e56eed52102b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-edge-servers-in-skype-for-business-server-2015"></a>Déploiement des serveurs Edge dans Skype Entreprise Server 2015
 
**Résumé :** Apprenez à déployer des serveurs de périphérie dans votre Skype pour environnement d’entreprise serveur 2015.
  
Les sections suivantes contiennent les étapes qui sont destinés à suivre après que le Skype pour obtenir la documentation 2015 de serveur d’entreprise de [planifier les déploiements de serveur de transport Edge dans Skype pour Business Server 2015](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) a été révisé. Les étapes de déploiement sont les suivantes :
  
- Interfaces réseau
    
- Installation
    
- Certificats
    
- Démarrer les serveurs Edge
    
## <a name="network-interfaces"></a>Interfaces réseau

Comme indiqué dans la planification, vous permet soit de configurer votre interface de réseau avec le système DNS dans le réseau de périmètre qui héberge vos serveurs Edge ou sans DNS dans le réseau de périmètre.
  
### <a name="interface-configuration-with-dns-servers-in-the-perimeter-network"></a>Configuration des interfaces avec des serveurs DNS dans le réseau de périmètre

1. Installez deux cartes réseau pour chaque serveur de transport Edge, un pour l’interface interne et celle de l’interface externe.
    
    > [!NOTE]
    > Les sous-réseaux interne et externe ne doivent pas être routables entre eux. 
  
2. Sur l’interface externe, vous allez configurer l' **une** des opérations suivantes :
    
   a. Trois adresses IP statiques sur le périmètre externe réseau sous-réseau et la passerelle par défaut vers l’interface interne du pare-feu externe de point. Configurer les paramètres DNS de carte pour pointer vers une paire de serveurs DNS de périmètre.
    
   b. Une des adresses IP statiques adresse sur le sous-réseau du réseau périmètre externe et pointez la passerelle par défaut vers l’interface interne du pare-feu externe. Configurer les paramètres DNS de carte pour pointer vers une paire de serveurs DNS de périmètre. Cette configuration n’est acceptable que si vous avez déjà configuré votre topologie pour que les valeurs non standard dans les affectations de port, qui est couvertes dans l’article [créer votre topologie de bord pour Skype pour Business Server 2015](create-your-edge-topology.md) .
    
3. Configurer une des adresses IP statiques sur le sous-réseau de réseau de périmètre interne sur votre interface interne et ne définissez pas une passerelle par défaut. Configurez les paramètres de la carte réseau DNS de manière à pointer vers au moins un serveur DNS, de préférence une paire de serveurs DNS de périmètre.
    
4. Créer des itinéraires statiques sur l’interface interne vers tous les réseaux internes où résident des clients, Skype pour Business Server 2015 et les serveurs de messagerie unifiée Exchange (MU).
    
### <a name="interface-configuration-without-dns-servers-in-the-perimeter-network"></a>Configuration des interfaces sans serveur DNS dans le réseau de périmètre

1. Installez deux cartes réseau pour chaque serveur de transport Edge, un pour l’interface interne et celle de l’interface externe.
    
    > [!NOTE]
    > Les sous-réseaux interne et externe ne doivent pas être routables entre eux. 
  
2. Sur l’interface externe, vous allez configurer l' **une** des opérations suivantes :
    
   a. Trois adresses IP statiques sur le périmètre externe sous-réseau du réseau. Vous devrez également configurer la passerelle par défaut sur l’interface externe, par exemple, définir le routeur faisant face à internet ou le pare-feu externe comme passerelle par défaut. Configurer les paramètres DNS de la carte pour pointer vers un serveur DNS externe, dans l’idéal, une paire de serveurs DNS externes.
    
   b. Une adresse IP statique sur le sous-réseau du réseau de périmètre extérieur. Vous devrez également configurer la passerelle par défaut sur l’interface externe, par exemple, définir le routeur faisant face à internet ou le pare-feu externe comme passerelle par défaut. Configurez les paramètres de la carte réseau DNS de manière à pointer vers une paire de serveurs DNS externes. Cette configuration n’est acceptable que si vous avez déjà configuré votre topologie pour que les valeurs non standard dans les affectations de port, qui est couvertes dans l’article [créer votre topologie de bord pour Skype pour Business Server 2015](create-your-edge-topology.md) .
    
3. Configurer une des adresses IP statiques sur le sous-réseau de réseau de périmètre interne sur votre interface interne et ne définissez pas une passerelle par défaut. Laissez les paramètres DNS de la carte réseau vides.
    
4. Créer des itinéraires statiques sur l’interface interne vers tous les réseaux internes où résident des clients, Skype pour Business Server 2015 et les serveurs de messagerie unifiée Exchange (MU).
    
5. Modifiez le fichier hôte sur chaque serveur de transport Edge pour contenir un enregistrement pour le serveur du tronçon suivant ou l’adresse IP virtuelle (VIP). Cet enregistrement sera le directeur, serveur Standard Edition server ou pool frontal que vous avez configuré comme l’adresse de tronçon suivant de serveur de transport Edge dans le Générateur de topologies. Si vous utilisez l’équilibrage de la charge DNS, inclure une ligne pour chaque membre de la grappe de tronçon suivante.
    
## <a name="installation"></a>Installation

Pour effectuer ces étapes correctement, vous devez avoir suivi les étapes décrites dans l’article [créer votre topologie de bord pour Skype pour Business Server 2015](create-your-edge-topology.md) .
  
1. Ouvrez une session sur le serveur que vous avez configurées pour le rôle serveur de transport Edge avec un compte qui se trouve dans le groupe Administrateurs local.
    
2. Vous aurez besoin du fichier de configuration de topologie que vous copié à la fin de la documentation de la topologie du serveur Edge sur cet ordinateur. Accédez au support externe (clé USB ou partage) sur lequel vous avez placé ce fichier de configuration.
    
3. Démarrez l' **Assistant de déploiement**.
    
4. Une fois que l’Assistant s’ouvre, cliquez sur **installation ou mise à jour des Skype pour système de serveur d’entreprise**.
    
5. L’Assistant s’exécutera vérifie pour voir si quelque chose est déjà installé. Comme il s’agit de la première exécution de l’Assistant, vous souhaiterez démarrer à l’étape 1 de **. Magasin de Configuration Local installation.**
    
6. La boîte de dialogue **configurer Local réplica de gestion centrale stocker** s’affiche. Vous devez cliquer sur **Importer à partir d’un fichier (recommandé pour les serveurs Edge)**.
    
7. De là, accédez à l’emplacement de la topologie exportée, sélectionnez le fichier .zip, cliquez sur **Ouvrir**, puis sur **Suivant**.
    
8. L’Assistant de déploiement de lire le fichier de configuration et écrire dans le fichier de configuration XML sur l’ordinateur local.
    
9. Une fois que la procédure **Exécution de commandes** est terminé, cliquez sur **Terminer**.
    
10. Dans l’Assistant déploiement, cliquez sur **étape 2. Installer ou supprimer Skype pour les composants serveur de Business**. L’Assistant va ensuite installer le Skype pour les composants Business Server 2015 bord spécifié dans le fichier de configuration XML stocké sur l’ordinateur local.
    
11. Une fois l’installation de l’ensemble, vous pouvez déplacer sur les étapes de la section **certificats** ci-dessous.
    
## <a name="certificates"></a>Certificats

La configuration requise du certificat pour le serveur de transport Edge, vous pouvez trouver dans la documentation de planification de certificat de bord. Les étapes de configuration des certificats figurent ci-dessous.
  
> [!NOTE]
> Lorsque vous exécutez l’Assistant de certificat, vous devez être connecté sous un compte disposant des autorisations appropriées pour le type de modèle de certificat que vous allez utiliser. Par défaut, un Skype pour la demande de certificat Business Server va utiliser le modèle de certificat de serveur Web. Si vous êtes connecté avec un compte qui est membre du groupe RTCUniversalServerAdmins pour demander un certificat à l’aide de ce modèle, assurez-vous que le groupe été attribué les autorisations d’inscription pour utiliser ce modèle. 
  
### <a name="internal-edge-interface-certificates"></a>Certificats d’interface interne de serveur Edge

 
### <a name="1-download-or-export-the-ca-certification-chain"></a>1. Téléchargez ou exporter de la chaîne de certification d’autorité de certification

 
#### <a name="nbspnbspnbsp-a-download-using-certsrv-web-site"></a>&nbsp;&nbsp;&nbsp;une barre d’outils. Télécharger à l’aide du site web certsrv

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;i. Ouvrez une session dans un Skype pour serveur Business Server 2015 dans votre réseau interne en tant que membre du groupe Administrateurs local.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;II. Ouvrez **Démarrer**, **exécuter** (ou de **recherche** et **exécuter** ), puis tapez ce qui suit :
    
  ```
  https://<NAME OF YOUR ISSUING CA SERVER>/certsrv
  ```

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Par exemple :
    
  ```
  https://ca01/contoso.com/certsrv
  ```

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;III. Dans la page de web de certsrv de l’autorité de certification émettrice, sous **Sélectionnez une tâche**, cliquez sur **télécharger un certificat CA, la chaîne de certificats ou CRL**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;IV. Sous **Télécharger un certificat d’autorité de certification, une chaîne de certificats ou la liste de révocation des certificats**, cliquez sur **Télécharger la chaîne du certificat de l’Autorité de certification**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;v. Dans la boîte de dialogue **Téléchargement de fichier**, cliquez sur **Enregistrer**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;VI. Enregistrez le fichier .p7b sur le lecteur de disque dur sur le serveur, puis le copier dans un dossier sur chacun de vos serveurs Edge.
    
### <a name="nbspnbspnbspb-export-using-mmc"></a>&nbsp;&nbsp;&nbsp;b. Exportation avec la console MMC

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;i. Vous pouvez exporter le certificat racine de l’autorité de certification à partir de tout ordinateur joint au domaine à l’aide de la console MMC. Sélectionnez **Démarrer** et **Exécuter** ou ouvrez **Recherche** et tapez **MMC** pour l’ouvrir.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;II. Dans la console MMC, cliquez sur **Fichier**, puis sur **Ajouter/supprimer un composant logiciel enfichable**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;III. Dans la boîte de dialogue **Ajouter ou supprimer des composants logiciels enfichables**, sélectionnez **Certificats**, puis cliquez sur **Ajouter**. Dans l’invite, sélectionnez **Compte d’ordinateur**, puis sur **Suivant**. Dans la boîte de dialogue **Sélectionner un ordinateur**, sélectionnez **Ordinateur local**. Cliquez sur **Terminer**, puis sur **OK**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;IV. Développez **certificats (ordinateur Local)**. Développez **autorités de Certification racines de confiance**. Sélectionnez **certificats**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;v. Cliquez sur le certificat racine émis par votre autorité de certification. Cliquez avec le bouton droit sur le certificat, sélectionnez **Toutes les tâches** dans le menu, puis sélectionnez **Exporter**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;VI. L’**Assistant Exportation du certificat** s’affiche. Cliquez sur **Suivant**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;VII. Dans la boîte de dialogue **Format du fichier d’exportation**, sélectionnez le format de l’exportation. L’option recommandée est **Standard de syntaxe de message cryptographique - Certificats PKCS #7 (P7b)**. Si tel est votre choix ainsi, n’oubliez pas également sélectionner la case à cocher **inclure tous les certificats dans le chemin d’accès de certification si possible** , que cette opération va exporter également de la chaîne de certificats, y compris le certificat d’autorité de certification racine et de tous les certificats intermédiaires. Cliquez sur **Suivant**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;VIII. Dans la boîte de dialogue **Fichier à exporter**, dans l’entrée de nom de fichier, tapez un nom et un chemin d’accès de fichier (l’extension par défaut est .p7b) pour le certificat exporté. S’il est plus facile de vous, cliquez sur le bouton **Parcourir** pour accéder à l’emplacement que vous souhaitez enregistrer le certificat exporté et nommez le certificat exporté ici. Cliquez sur **Enregistrer**, puis cliquez sur **suivant** lorsque vous êtes prêt.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;IX. Consultez le résumé de vos actions et cliquez sur **Terminer** pour achever l’exportation du certificat. Cliquez sur **OK** pour confirmer l’exportation.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;x. Copier le fichier .p7b sur chacun de vos serveurs Edge.
    
### <a name="2-import-the-ca-certification-chain"></a>2. importation de la chaîne de certification d’autorité de certification

&nbsp;&nbsp;&nbsp;une barre d’outils. Sur chaque serveur Edge, ouvrez la console MMC (cliquez sur **Démarrer** et **exécuter**ou **Rechercher**et tapez **MMC** pour ouvrir).
    
&nbsp;&nbsp;&nbsp;b. Dans le menu **Fichier**, cliquez sur **Ajouter/Supprimer un composant logiciel enfichable**, puis sur **Ajouter**.
    
&nbsp;&nbsp;&nbsp;c. Dans la boîte de dialogue **Ajouter ou supprimer des composants logiciels enfichables**, cliquez sur **Certificats**, puis sur **Ajouter**.
    
&nbsp;&nbsp;&nbsp;d. Dans la boîte de dialogue **Composant logiciel enfichable Certificats**, cliquez sur **Compte d’ordinateur**, puis sur **Suivant**.
    
&nbsp;&nbsp;&nbsp;e. Dans la boîte de dialogue **Sélectionner un ordinateur**, assurez-vous que la case à cocher **Ordinateur local : (l’ordinateur sur lequel cette console s’exécute)** est activée, puis cliquez sur **Terminer**.
    
&nbsp;&nbsp;&nbsp;f. Cliquez sur **Fermer**, puis sur **OK**.
    
&nbsp;&nbsp;&nbsp;g. Dans l’arborescence de la console, développez **Certificats (ordinateur local)**, cliquez avec le bouton droit sur **Autorités de certification racines de confiance**, sélectionnez **Toutes les tâches**, puis cliquez sur **Importer**.
    
&nbsp;&nbsp;&nbsp;h. Dans l’Assistant qui s’affiche, dans la zone **Fichier à importer**, spécifiez le nom de fichier du certificat (nom attribué au fichier .p7b dans la section précédente). Cliquez sur **Suivant**.
    
&nbsp;&nbsp;&nbsp;i. Laissez la case d’option **Placer tous les certificats dans le magasin suivant comme autorités de certification racines approuvées** activée. Cliquez sur **Suivant**.
    
&nbsp;&nbsp;&nbsp;j. Consultez le résumé, puis cliquez sur **Terminer** pour finaliser l’importation.
    
&nbsp;&nbsp;&nbsp;k. Cela doit être fait pour chaque serveur de transport Edge du déploiement.
    
### <a name="3-create-the-certificate-request"></a>3. création de la demande de certificat

&nbsp;&nbsp;&nbsp;une barre d’outils. Ouvrez une session sur un de vos serveurs Edge, lancez l’Assistant Déploiement et sous **étape 3 : demande, installation ou attribuer des certificats**, cliquez sur **exécuter** (ou **Exécuter une nouvelle fois**, si vous avez déjà exécuté cet Assistant).
    
&nbsp;&nbsp;&nbsp;b. Dans la page **Demande de certificat**, assurez-vous que l’option **Certificat Edge interne** est sélectionnée, puis cliquez sur **Demande**.
    
&nbsp;&nbsp;&nbsp;c. Dans la page **Demandes différées ou immédiates**, sélectionnez **Envoyer la demande immédiatement à une autorité de certification en ligne** si vous avez accès à une telle autorité à partir de votre environnement de serveur Edge ou **Préparer la demande maintenant, mais l’envoyer ultérieurement** autrement.
    
&nbsp;&nbsp;&nbsp;d. Dans la page **Fichier de demande de certificat**, saisissez le composant complet et le nom de fichier de l’emplacement où le fichier sera enregistré (par exemple, c:\SkypeInternalEdgeCert.cer). Cliquez sur **Suivant**.
    
&nbsp;&nbsp;&nbsp;e. Dans la page **Spécifier un autre modèle de certificat**, pour utiliser un autre modèle que le modèle Serveur web par défaut, activez la case à cocher **Utiliser un autre modèle de certificat pour l’autorité de certification sélectionnée**. Autrement, ne faites rien.
    
&nbsp;&nbsp;&nbsp;f. Dans la page Nom et paramètres de sécurité, procédez comme suit :
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;i. Dans **Nom convivial**, saisissez le nom complet du certificat (par exemple, Périmètre interne).
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;II. Dans **Longueur en bits**, sélectionnez la longueur exprimée en bits (la valeur par défaut est 2048, vous pouvez l’augmenter pour plus de sécurité, mais cela ralentit les performances).
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;III. Si vous avez besoin d’un certificat exportable, vous devez activer la case à cocher **Marquer la clé privée du certificat comme exportable**.
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;IV. Cliquez sur **Suivant**.
    
&nbsp;&nbsp;&nbsp;g. Dans la page **Informations relatives à l’organisation**, entrez le nom de votre organisation et de votre unité d’organisation). Vous pouvez entrer votre division ou service (Informatique, par exemple).
    
&nbsp;&nbsp;&nbsp;h. Dans la page **Informations géographiques**, saisissez les informations d’emplacement.
    
&nbsp;&nbsp;&nbsp;i. Dans la page **Nom du sujet/Autres noms du sujet**, l’Assistant renseigne automatiquement les informations.
    
&nbsp;&nbsp;&nbsp;j. Dans la page **Configurer d’autres noms du sujet supplémentaires**, ajoutez les autres noms du sujet supplémentaires nécessaires.
    
&nbsp;&nbsp;&nbsp;k. Sur la page de **Résumé de la demande** , passez en revue les informations de certificat qui vont être utilisé pour générer votre requête. Si vous devez apporter des modifications, revenez en arrière pour le faire.
    
&nbsp;&nbsp;&nbsp;l. Puis cliquez sur **suivant** pour générer le fichier conseiller du service clientèle que vous devrez fournir à l’autorité de certification (vous pouvez également cliquer sur **Afficher le journal** pour consulter le journal des demandes de certificats).
    
&nbsp;&nbsp;&nbsp;m. Une fois la demande générée, vous pouvez cliquer sur **Afficher** pour consulter le certificat et sur **Terminer** pour fermer la fenêtre. Le contenu du fichier CSR doit être affecté à votre autorité de certification afin qu’elle puisse générer un certificat que vous pourrez importer sur cet ordinateur dans la section suivante.
    

### <a name="4-import-the-certificate"></a>4. importer le certificat

&nbsp;&nbsp;&nbsp;une barre d’outils. Ouvrez une session, en tant que membre du groupe d’administrateurs local sur le serveur Edge que vous avez apportées à votre demande de certificat à partir de dans la dernière procédure.
    
&nbsp;&nbsp;&nbsp;b. Dans l’Assistant de déploiement, en regard de **étape 3. Demander, installer ou attribuer des certificats**, cliquez sur **Exécuter à nouveau**.
    
&nbsp;&nbsp;&nbsp;c. Dans la page **Tâches se rapportant aux certificats disponibles**, cliquez sur **Importer un certificat à partir d’un fichier .P7b, .pfx ou .cer**.
    
&nbsp;&nbsp;&nbsp;d. Dans la page **Importer un certificat**, tapez le chemin complet et le nom du fichier du certificat que vous avez reçu dans la section précédent (ou cliquez sur **Parcourir** pour rechercher et sélectionner le fichier).
    
&nbsp;&nbsp;&nbsp;e. Si vous importez des certificats pour d’autres membres de votre pool de bord et votre certificat contient une clé privée, veillez à sélectionner la case à cocher **fichier de certificat qui contient la clé privée du certificat** et de spécifier le mot de passe. Cliquez sur **Suivant** pour continuer.
    
&nbsp;&nbsp;&nbsp;f. Dans la page**Résumé** , cliquez sur **suivant** une fois que vous avez confirmé les informations et **Terminer** une fois que le certificat est importé avec succès.
    
 
### <a name="5-export-the-certificate"></a>5. exportation du certificat

&nbsp;&nbsp;&nbsp;une barre d’outils. Assurez-vous que vous avez ouvert une session sur le serveur Edge vous avez importé précédemment, le certificat en tant que membre du groupe Administrateurs local.
    
&nbsp;&nbsp;&nbsp;b. Cliquez sur **Démarrer**, sur **exécuter** (ou ouvrez la **recherche** ), puis tapez **MMC**.
    
&nbsp;&nbsp;&nbsp;c. Dans la console MMC, cliquez sur **Fichier**, puis sur **Ajouter/Supprimer un composant logiciel enfichable**.
    
&nbsp;&nbsp;&nbsp;d. Dans la boîte de dialogue **Ajouter ou supprimer des composants logiciels enfichables**, cliquez sur **Certificats**, puis sur **Ajouter**.
    
&nbsp;&nbsp;&nbsp;e. Dans la boîte de dialogue composant logiciel enfichable **certificats** , sélectionnez **compte d’ordinateur**. Cliquez sur **Suivant**.
    
&nbsp;&nbsp;&nbsp;f. Dans la boîte de dialogue **Sélectionner un ordinateur**, sélectionnez **Ordinateur local : (l’ordinateur sur lequel cette console s’exécute)**. Cliquez sur **Terminer**. Cliquez sur **OK**, et la configuration de la console MMC est terminée.
    
&nbsp;&nbsp;&nbsp;g. Double-cliquez sur **Certificats (ordinateur local)** pour développer les magasins de certificats. Double-cliquez sur **personnel**, puis cliquez sur **certificats**.
    
  > [!NOTE]
  > Vous êtes peut-être ici, et vous ne voyez pas tous les certificats dans les certificats personnels stocker pour l’ordinateur local. Vous n’avez pas besoin de recherche, si la clé ne 's pas, le texte importé certificat n’ont une clé privée qui lui est associée. Essayez de la demande et importer les étapes ci-dessus une fois de plus et si vous êtes sûr de qu'avoir tout ce droit, contactez votre administrateur d’autorité de certification ou le fournisseur. 
  
&nbsp;&nbsp;&nbsp;h. Dans le **stockage de certificats personnels** pour l’ordinateur local, cliquez sur le certificat que vous exportez. Sélectionnez **Toutes les tâches** dans le menu qui s’affiche, puis cliquez sur **Exporter**.
    
&nbsp;&nbsp;&nbsp;i. Dans l’**Assistant Exportation du certificat**, cliquez sur **Suivant**. Sélectionnez **Oui, exporter la clé privée**. Cliquez sur **Suivant**.
    
&nbsp;&nbsp;&nbsp;j. Dans la boîte de dialogue **Exporter les formats de fichiers**, sélectionnez **Échange d’informations personnelles – PKCS#12 (.PFX)**, puis les éléments suivants :
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;i. Incluez tous les certificats dans le chemin d’accès de certification, si possible.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;II. Exportez toutes les propriétés étendues.
    
   > [!NOTE]
   > Ne sélectionnez **JAMAIS****Supprimer la clé privée si l’exportation s’est terminée correctement**. Il allez devoir vous réimportez le certificat et la clé privée à ce serveur de transport Edge.
  
&nbsp;&nbsp;&nbsp;k. Si vous souhaitez affecter un mot de passe pour protéger la clé privée, vous pouvez taper un mot de passe pour cette clé. Entrez de nouveau le mot de passe pour le confirmer, puis cliquez sur **Suivant**.
    
&nbsp;&nbsp;&nbsp;l. Tapez un chemin d’accès et un nom de fichier avec l’extension **.pfx** pour le certificat exporté. Le chemin d’accès soit doit être accessible par les autres serveurs de bord dans le pool, ou vous devez déplacer le fichier au moyen d’un support externe (par exemple, une clé USB). Lorsque vous avez fait votre choix, cliquez sur **suivant** .
    
&nbsp;&nbsp;&nbsp;m. Consultez le résumé dans la boîte de dialogue **Fin de l’Assistant Exportation du certificat**, puis cliquez sur **Terminer**.
    
&nbsp;&nbsp;&nbsp;n. Cliquez sur **OK** dans la boîte de dialogue indiquant que l’exportation a abouti.
    
 
### <a name="6-assign-the-certificate"></a>6. attribution du certificat

&nbsp;&nbsp;&nbsp;une barre d’outils. Sur chaque serveur Edge, dans l’Assistant de déploiement, en regard de **étape 3. Demander, installer ou attribuer des certificats**, cliquez sur **exécuter**.
    
&nbsp;&nbsp;&nbsp;b. Dans la page **Tâches se rapportant aux certificats disponibles**, cliquez sur **Affecter un certificat existant**.
    
&nbsp;&nbsp;&nbsp;c. Dans la page **Affectation de certificat**, sélectionnez **Serveur Edge interne** dans la liste.
    
&nbsp;&nbsp;&nbsp;d. Dans la page **Magasin de certificats** , sélectionnez le certificat que vous avez importés pour la bordure interne (à partir de la section précédente).
    
&nbsp;&nbsp;&nbsp;e. Dans la page **Résumé de l’affectation du certificat**, vérifiez vos paramètres, puis cliquez sur **Suivant** pour affecter le certificat.
    
&nbsp;&nbsp;&nbsp;f. Dans la page de fin de l’Assistant, cliquez sur **Terminer**.
    
&nbsp;&nbsp;&nbsp;g. Une fois que vous avez terminé cette procédure, il est recommandé, pour ouvrir le composant logiciel enfichable MMC certificats sur chaque serveur Edge, développez **certificats (ordinateur Local)**, développez **personnel**, cliquez sur **certificats**et confirmez que le bord interne certificat est répertorié dans le volet de détails.
    
### <a name="external-edge-interface-certificates"></a>Certificats d’interface externe de serveur Edge

 
### <a name="1-create-the-certificate-request"></a>1. créer la demande de certificat

&nbsp;&nbsp;&nbsp;une barre d’outils. Ouvrez une session sur un de vos serveurs Edge, lancez l’Assistant Déploiement et sous **étape 3 : demande, installation ou attribuer des certificats, cliquez sur Exécuter** (ou l' **Exécuter à nouveau**, si vous avez déjà exécuté cet Assistant).
    
&nbsp;&nbsp;&nbsp;b. Dans la page **Tâches se rapportant aux certificats disponibles**, cliquez sur **Créer une demande de certificat**.
    
&nbsp;&nbsp;&nbsp;c. Dans la page **Demande de certificat**, assurez-vous que l’option **Certificat Edge externe** est sélectionnée, puis cliquez sur **Suivant**.
    
&nbsp;&nbsp;&nbsp;d. Dans la page **Demandes différées ou immédiates**, cliquez sur **Préparer la demande, mais ne pas l’envoyer maintenant**.
    
&nbsp;&nbsp;&nbsp;e. Dans la page **Fichier de demande de certificat**, saisissez le composant complet et le nom de fichier de l’emplacement où le fichier sera enregistré (par exemple, c:\SkypeInternalEdgeCert.cer). Cliquez sur **Suivant**.
    
&nbsp;&nbsp;&nbsp;f. Dans la page **Spécifier un autre modèle de certificat**, pour utiliser un autre modèle que le modèle Serveur web par défaut, activez la case à cocher **Utiliser un autre modèle de certificat pour l’autorité de certification sélectionnée**.
    
&nbsp;&nbsp;&nbsp;g. Dans la page Nom et paramètres de sécurité, procédez comme suit :
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;i. Dans **Nom convivial**, saisissez le nom complet du certificat (par exemple, Périmètre externe).
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;II. Dans **Longueur en bits**, sélectionnez la longueur exprimée en bits (la valeur par défaut est 2048, vous pouvez l’augmenter pour plus de sécurité, mais cela ralentit les performances).
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;III. Si vous avez besoin d’un certificat exportable, vous devez activer la case à cocher **Marquer la clé privée du certificat comme exportable**.
    
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;IV. Cliquez sur **Suivant**.
    
&nbsp;&nbsp;&nbsp;h. Dans la page **Informations relatives à l’organisation**, entrez le nom de votre organisation et de votre unité d’organisation). Vous pouvez entrer votre division ou service (Informatique, par exemple).
    
&nbsp;&nbsp;&nbsp;i. Dans la page **Informations géographiques**, saisissez les informations d’emplacement.
    
&nbsp;&nbsp;&nbsp;j. Dans la page **Nom du sujet/Autres noms du sujet**, l’Assistant renseigne automatiquement les informations nécessaires.
    
&nbsp;&nbsp;&nbsp;k. Dans la page **Paramètre de domaine SIP sur les noms de sujet alternatifs (SAN)** , cochez la case de domaine pour ajouter un sip.<sipdomain> entrée à la liste d’autres noms de sujet.
    
&nbsp;&nbsp;&nbsp;l. Dans la page **Configurer d’autres noms du sujet supplémentaires**, ajoutez les autres noms du sujet supplémentaires nécessaires.
    
&nbsp;&nbsp;&nbsp;m. Sur la page de **Résumé de la demande** , passez en revue les informations de certificat qui vont être utilisé pour générer votre requête. Si vous devez apporter des modifications, revenez en arrière pour le faire.
    
&nbsp;&nbsp;&nbsp;n. Lorsque vous êtes prêt, cliquez sur **suivant** pour générer le fichier conseiller du service clientèle que vous devrez fournir à l’autorité de certification (vous pouvez également cliquer sur **Afficher le journal** pour consulter le journal des demandes de certificats).
    
&nbsp;&nbsp;&nbsp;o. Une fois la demande générée, vous pouvez cliquer sur **Afficher** pour consulter le certificat et sur **Terminer** pour fermer la fenêtre. Le contenu du fichier CSR doit être affecté à votre autorité de certification afin qu’elle puisse générer un certificat que vous pourrez importer sur cet ordinateur dans la section suivante.
    
&nbsp;&nbsp;&nbsp;p. (FACULTATIF) Il est possible que vous soyez invité à fournir certaines informations lors de l’envoi de la demande de signature de certificat (CSR), comme suit (les autorités de certification varient considérablement, de sorte que ce n’est peut-être pas obligatoire) :
    
  - **Microsoft** comme plateforme serveur
    
  - **Services Internet (IIS)** comme version
    
  - **Serveur web** comme type d’utilisation
    
  - **PKCS7** comme réponse
    
 
### <a name="2-import-the-certificate"></a>2. importation du certificat

&nbsp;&nbsp;&nbsp;une barre d’outils. Ouvrez une session, en tant que membre du groupe d’administrateurs local sur le serveur Edge que vous avez apportées à votre demande de certificat à partir de dans la dernière procédure.
    
&nbsp;&nbsp;&nbsp;b. Dans l’Assistant de déploiement, en regard de **étape 3. Demander, installer ou attribuer des certificats**, cliquez sur **Exécuter à nouveau**.
    
&nbsp;&nbsp;&nbsp;c. Dans la page **Tâches se rapportant aux certificats disponibles**, cliquez sur **Importer un certificat à partir d’un fichier .P7b, .pfx ou .cer**.
    
&nbsp;&nbsp;&nbsp;d. Dans la page **Importer un certificat**, tapez le chemin complet et le nom du fichier du certificat que vous avez reçu dans la section précédent (ou cliquez sur **Parcourir** pour rechercher et sélectionner le fichier). Si votre certificat contient une clé privée, veillez à sélectionner le **fichier de certificat contient la clé privée du certificat**et entrez le mot de passe pour la clé privée. Cliquez sur **Suivant** pour continuer.
    
&nbsp;&nbsp;&nbsp;e. Dans la page **Importer le résumé du certificat**, vérifiez les informations résumées, puis cliquez sur **Suivant**.
    
&nbsp;&nbsp;&nbsp;f. Sur la page **En cours d’exécution des commandes** , vous pouvez consulter le résultat de l’importation, lorsqu’elle est terminée en cliquant sur **Afficher le journal**. Cliquez sur **Terminer** pour terminer l’importation du certificat.
    
&nbsp;&nbsp;&nbsp;g. Si vous disposez d’autres serveurs de périphérie dans un pool, vous devez suivre les deux procédures suivantes ainsi. S’il s’agit d’un serveur de bord autonome, vous avez terminé avec les certificats externes.
    
 
### <a name="3-export-the-certificate"></a>3. exporter le certificat

&nbsp;&nbsp;&nbsp;une barre d’outils. Assurez-vous que vous avez ouvert une session sur le serveur Edge vous avez importé le certificat en tant qu’administrateur local.
    
&nbsp;&nbsp;&nbsp;b. Cliquez sur **Démarrer**, sur **exécuter** (ou ouvrez la **recherche** ), puis tapez **MMC**.
    
&nbsp;&nbsp;&nbsp;c. Dans la console MMC, cliquez sur **Fichier**, puis sur **Ajouter/Supprimer un composant logiciel enfichable**.
    
&nbsp;&nbsp;&nbsp;d. Dans la boîte de dialogue **Ajouter ou supprimer des composants logiciels enfichables**, cliquez sur **Certificats**, puis sur **Ajouter**.
    
&nbsp;&nbsp;&nbsp;e. Dans la boîte de dialogue composant logiciel enfichable **certificats** , sélectionnez **compte d’ordinateur**. Cliquez sur **Suivant**.
    
&nbsp;&nbsp;&nbsp;f. Dans la boîte de dialogue **Sélectionner un ordinateur**, sélectionnez **Ordinateur local : (l’ordinateur sur lequel cette console s’exécute)**. Cliquez sur **Terminer**. Cliquez sur **OK**, et la configuration de la console MMC est terminée.
    
&nbsp;&nbsp;&nbsp;g. Double-cliquez sur **Certificats (ordinateur local)** pour développer les magasins de certificats. Double-cliquez sur **Personnel**, puis sur **Certificats**.
    
    > [!NOTE]
    > You may be here, and you don't see any certificates in the Certificates Personal store for the local computer. You don't need to hunt around, if the key's not there, the imported certificate didn't have a private key associated with it. Try the request and import steps above one more time, and if you're sure you got all that right, talk to your CA administrator or provider. 
  
&nbsp;&nbsp;&nbsp;h. Dans le **stockage de certificats personnels** pour l’ordinateur local, cliquez sur le certificat que vous exportez. Sélectionnez **Toutes les tâches** dans le menu qui s’affiche, puis cliquez sur **Exporter**.
    
&nbsp;&nbsp;&nbsp;i. Dans l’**Assistant Exportation du certificat**, cliquez sur **Suivant**. Sélectionnez **Oui, exporter la clé privée**. Cliquez sur **Suivant**.
    
    > [!NOTE]
    > If **Yes, export the private key** isn't available, then the private key for this certificate wasn't marked for export before you got it. You need to request the certificate from the provider again, with the private key set to export, before doing this successfully.
  
&nbsp;&nbsp;&nbsp;j. Dans la boîte de dialogue Exporter les formats de fichiers, sélectionnez Échange d’informations personnelles – PKCS#12 (.PFX), puis les éléments suivants :
    
 &nbsp;&nbsp;&nbsp;i. Incluez tous les certificats dans le chemin d’accès de certification, si possible.
    
 &nbsp;&nbsp;&nbsp;II. Exportez toutes les propriétés étendues.
    
    > [!NOTE]
    > **NEVER** select **Delete the private key if the export is successful**. It'll mean you have to reimport the certificate and private key back to this Edge Server.
  
&nbsp;&nbsp;&nbsp;k. Si vous souhaitez affecter un mot de passe pour protéger la clé privée, vous pouvez taper un mot de passe pour cette clé. Entrez de nouveau le mot de passe pour le confirmer, puis cliquez sur **Suivant**.
    
&nbsp;&nbsp;&nbsp;l. Tapez un chemin d’accès et un nom de fichier avec l’extension **.pfx** pour le certificat exporté. Le chemin d’accès soit doit être accessible par les autres serveurs de bord dans le pool, ou vous devez déplacer le fichier au moyen d’un support externe (par exemple, une clé USB). Lorsque vous avez fait votre choix, cliquez sur **suivant** .
    
&nbsp;&nbsp;&nbsp;m. Consultez le résumé dans la boîte de dialogue **Fin de l’Assistant Exportation du certificat**, puis cliquez sur **Terminer**.
    
&nbsp;&nbsp;&nbsp;n. Cliquez sur **OK** dans la boîte de dialogue indiquant que l’exportation a abouti.
    
&nbsp;&nbsp;&nbsp;o. Vous devez maintenant revenir à l’importation la section certificat antérieurement et importer le certificat sur tous vos serveurs Edge restantes, puis poursuivre l’affectation, ci-dessous.
    
 
### <a name="4-assign-the-certificate"></a>4. Attribuez le certificat

&nbsp;&nbsp;&nbsp;une barre d’outils. Sur **chaque** serveur de bord, dans l’Assistant de déploiement, en regard de **étape 3. Demander, installer ou attribuer des certificats**, cliquez sur **exécuter**.
    
&nbsp;&nbsp;&nbsp;b. Dans la page **Tâches se rapportant aux certificats disponibles**, cliquez sur **Affecter un certificat existant**.
    
&nbsp;&nbsp;&nbsp;c. Dans la page **Attribution du certificat** , sélectionnez **Bord externe** dans la liste.
    
&nbsp;&nbsp;&nbsp;d. Dans la page **Magasin de certificats** , sélectionnez le certificat que vous avez importés pour la périphérie externe (à partir de la section précédente).
    
&nbsp;&nbsp;&nbsp;e. Dans la page **Résumé de l’affectation du certificat**, vérifiez vos paramètres, puis cliquez sur **Suivant** pour affecter le certificat.
    
&nbsp;&nbsp;&nbsp;f. Dans la page de fin de l’Assistant, cliquez sur **Terminer**.
    
&nbsp;&nbsp;&nbsp;g. Une fois que vous avez terminé cette procédure, il est recommandé, pour ouvrir le composant logiciel enfichable MMC certificats sur chaque serveur, développez **certificats (ordinateur Local)**, développez **personnel**, cliquez sur **certificats**et confirmez que le bord interne certificat est répertorié dans le volet de détails.
    
   > [!NOTE]
    > Vous devez également configurer les certificats pour votre serveur de proxy inverse. Qui est couvert dans les serveurs Proxy d’annuler le programme d’installation pour Skype pour Business Server 2015 rubrique. 
  
## <a name="starting-the-edge-servers"></a>Démarrer les serveurs Edge

Une fois l’installation terminée, vous devez démarrer les services sur chaque serveur de transport Edge dans votre déploiement :
  
1. Sur chaque serveur de transport Edge, dans l' **Assistant de déploiement**, à côté **étape 4 : démarrez les Services de**, cliquez sur **exécuter**.
    
2. Sur la page de **Démarrage de Skype pour les Services de serveur** , passer en revue la liste des services, puis cliquez sur **suivant** pour démarrer les services.
    
3. Une fois les services lancés, cliquez sur **Terminer** pour fermer l’Assistant.
    
4. (Facultatif) Toujours sous l’**Étape 4 : Lancement des services**, cliquez sur **État des services**.
    
5.  Dans la console **MMC des Services** sur chaque serveur, vérifiez que tous le Skype pour les services d’entreprise serveur 2015 sont en cours d’exécution.
    

