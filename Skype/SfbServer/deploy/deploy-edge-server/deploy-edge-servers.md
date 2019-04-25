---
title: Déployer des serveurs de périphérie dans Skype pour Business Server
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 63c7251c-080a-4175-99a6-f86d0266d6bc
description: 'Résumé : Apprenez à déployer des serveurs de périphérie dans votre Skype pour un environnement de serveur d’entreprise.'
ms.openlocfilehash: e8e3251380c996ca4fea65fd286ef9e2a9d75575
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32223809"
---
# <a name="deploy-edge-servers-in-skype-for-business-server"></a>Déployer des serveurs de périphérie dans Skype pour Business Server
 
**Résumé :** Apprenez à déployer des serveurs de périphérie dans votre Skype pour un environnement de serveur d’entreprise.
  
Les sections suivantes contiennent des étapes qui sont destinées à être suivi une fois le Skype pour la documentation Business Server [Planifier pour les déploiements de serveur de transport Edge dans Skype pour Business Server](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) a été passé en revue. Les étapes de déploiement sont les suivantes :
  
- Interfaces réseau
    
- Installation
    
- Certificats
    
- Démarrer les serveurs de périphérie
    
## <a name="network-interfaces"></a>Interfaces réseau

Comme indiqué dans la planification, vous allez soit configurer votre interface réseau avec le système DNS dans le réseau de périmètre qui héberge vos serveurs Edge ou sans DNS dans le réseau de périmètre.
  
### <a name="interface-configuration-with-dns-servers-in-the-perimeter-network"></a>Configuration des interfaces avec des serveurs DNS dans le réseau de périmètre

1. Installez deux cartes réseau pour chaque serveur Edge, un pour l’interface interne et un pour l’interface externe.
    
    > [!NOTE]
    > Les sous-réseaux interne et externe ne doivent pas être routables entre eux. 
  
2. Sur l’interface externe, vous allez configurer **une** des options suivantes :
    
   a. Trois adresses IP statiques sur le périmètre externe sous-réseau de réseau et point de la passerelle par défaut à l’interface interne du pare-feu externe. Configurer les paramètres DNS de carte pour pointer vers une paire de serveurs DNS de périmètre.
    
   b. Une adresse IP statique adresse sur le sous-réseau de réseau de périmètre externe et pointez sur la passerelle par défaut à l’interface interne du pare-feu externe. Configurer les paramètres DNS de carte pour pointer vers une paire de serveurs DNS de périmètre. Cette configuration n’est acceptable si vous avez précédemment configuré votre topologie pour que les valeurs non standard dans les ports, est abordée dans l’article [créer votre topologie du périmètre pour Skype pour Business Server](create-your-edge-topology.md) .
    
3. Sur l’interface interne, configurez une adresse IP statique sur le sous-réseau de réseau de périmètre interne et ne définissez pas une passerelle par défaut. Configurez les paramètres de la carte réseau DNS de manière à pointer vers au moins un serveur DNS, de préférence une paire de serveurs DNS de périmètre.
    
4. Créez des itinéraires statiques persistants sur l’interface interne vers tous les réseaux internes où résident les clients, Skype pour Business Server et les serveurs de messagerie unifiée Exchange (MU).
    
### <a name="interface-configuration-without-dns-servers-in-the-perimeter-network"></a>Configuration des interfaces sans serveur DNS dans le réseau de périmètre

1. Installez deux cartes réseau pour chaque serveur Edge, un pour l’interface interne et un pour l’interface externe.
    
    > [!NOTE]
    > Les sous-réseaux interne et externe ne doivent pas être routables entre eux. 
  
2. Sur l’interface externe, vous allez configurer **une** des options suivantes :
    
   a. Trois adresses IP statiques sur le périmètre externe sous-réseau du réseau. Vous devrez également configurer la passerelle par défaut sur l’interface externe, par exemple, définissant le routeur internet ou le pare-feu externe comme passerelle par défaut. Configurer les paramètres DNS de carte pour pointer vers un serveur DNS externe, de préférence une paire de serveurs DNS externes.
    
   b. Une adresse IP statique sur le sous-réseau du réseau de périmètre extérieur. Vous devrez également configurer la passerelle par défaut sur l’interface externe, par exemple, définissant le routeur internet ou le pare-feu externe comme passerelle par défaut. Configurez les paramètres de la carte réseau DNS de manière à pointer vers une paire de serveurs DNS externes. Cette configuration n’est acceptable si vous avez précédemment configuré votre topologie pour que les valeurs non standard dans les ports, est abordée dans l’article [créer votre topologie du périmètre pour Skype pour Business Server](create-your-edge-topology.md) .
    
3. Sur l’interface interne, configurez une adresse IP statique sur le sous-réseau de réseau de périmètre interne et ne définissez pas une passerelle par défaut. Laissez les paramètres DNS de la carte réseau vides.
    
4. Créez des itinéraires statiques persistants sur l’interface interne vers tous les réseaux internes où résident les clients, Skype pour Business Server et les serveurs de messagerie unifiée Exchange (MU).
    
5. Modifiez le fichier hôte sur chaque serveur de périphérie pour contenir un enregistrement pour le serveur du tronçon suivant ou adresse IP virtuelle (VIP). Cet enregistrement sera le directeur, serveur Standard Edition server ou pool frontal que vous avez configuré en tant que l’adresse du tronçon suivant de serveur de transport Edge dans le Générateur de topologie. Si vous utilisez l’équilibrage de charge DNS, inclure une ligne pour chaque membre du pool du tronçon suivant.
    
## <a name="installation"></a>Installation

Pour effectuer ces étapes avec succès, vous devez avoir suivi les étapes dans l’article [créer votre topologie du périmètre pour Skype pour Business Server](create-your-edge-topology.md) .
  
1. Ouvrez une session sur le serveur que vous avez configurées pour le rôle serveur de transport Edge avec un compte qui se trouve dans le groupe administrateur local.
    
2. Vous devez le fichier de configuration de topologie que vous avez copié à la fin de la documentation de la topologie du serveur Edge sur cet ordinateur. Accédez au support externe (clé USB ou partage) sur lequel vous avez placé ce fichier de configuration.
    
3. Démarrez l' **Assistant Déploiement**.
    
4. Une fois que l’Assistant s’ouvre, cliquez sur **installer ou mise à jour Skype pour le système de serveur d’entreprise**.
    
5. L’Assistant sera exécuté vérifie si rien est déjà installé. Comme il s’agit de la première exécution de l’Assistant, vous souhaiterez commencent à **étape 1. Installer le magasin de Configuration Local.**
    
6. La boîte de dialogue **configurer Local réplica de gestion centrale magasin** s’affiche. Vous devez cliquer sur **Importer à partir d’un fichier (recommandé pour les serveurs Edge)**.
    
7. De là, accédez à l’emplacement de la topologie exportée, sélectionnez le fichier .zip, cliquez sur **Ouvrir**, puis sur **Suivant**.
    
8. L’Assistant Déploiement de lire le fichier de configuration et écrire le fichier de configuration XML sur l’ordinateur local.
    
9. Une fois que la procédure **Exécution de commandes** est terminé, cliquez sur **Terminer**.
    
10. Dans l’Assistant déploiement, cliquez sur **étape 2. Installer ou supprimer des Skype pour les composants du serveur Business**. L’Assistant installe alors le Skype pour les composants serveur Edge Server Business spécifié dans le fichier de configuration XML stocké sur l’ordinateur local.
    
11. Une fois l’installation de l’ensemble, vous pouvez déplacer sur les étapes décrites dans la section **certificats** ci-dessous.
    
## <a name="certificates"></a>Certificats

Vous trouverez les certificats requis pour le serveur de périphérie dans la documentation de planification de certificat de serveur Edge. Les étapes de configuration des certificats figurent ci-dessous.
  
> [!NOTE]
> Lorsque vous exécutez l’Assistant certificat, vous devez être connecté sous un compte disposant des autorisations appropriées pour le type de modèle de certificat que vous allez utiliser. Par défaut, un Skype pour la demande de certificat Business Server va utiliser le modèle de certificat de serveur Web. Si vous êtes connecté avec un compte qui est membre du groupe RTCUniversalServerAdmins pour demander un certificat par le biais de ce modèle, assurez-vous que le groupe reçu les autorisations de s’inscrire pour utiliser ce modèle. 
  
### <a name="internal-edge-interface-certificates"></a>Certificats d’interface interne de serveur Edge

 
### <a name="1-download-or-export-the-ca-certification-chain"></a>1. Téléchargez ou d’exportation de la chaîne de certification d’autorité de certification

 
#### <a name="nbspnbspnbsp-a-download-using-certsrv-web-site"></a>&nbsp;&nbsp;&nbsp;un. Télécharger à l’aide du site web certsrv

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;i. Connectez-vous à un Skype pour Business Server dans votre réseau interne en tant que membre du groupe Administrateurs local.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;II. Ouvrez **Démarrer**, **exécuter** (ou **recherche** et **exécutez** ), puis tapez ce qui suit :
    
  ```
  https://<NAME OF YOUR ISSUING CA SERVER>/certsrv
  ```

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Par exemple :
    
  ```
  https://ca01/contoso.com/certsrv
  ```

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;III. Dans la page web certsrv de l’autorité de certification émettrice, sous **Sélectionnez une tâche**, cliquez sur **télécharger un certificat autorité de certification, chaîne de certificats ou une liste de révocation**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;IV. Sous **Télécharger un certificat d’autorité de certification, une chaîne de certificats ou la liste de révocation des certificats**, cliquez sur **Télécharger la chaîne du certificat de l’Autorité de certification**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;v. Dans la boîte de dialogue **Téléchargement de fichier**, cliquez sur **Enregistrer**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;VI. Enregistrez le fichier .p7b sur le disque dur du serveur, puis le copier dans un dossier sur chacun de vos serveurs Edge.
    
### <a name="nbspnbspnbspb-export-using-mmc"></a>&nbsp;&nbsp;&nbsp;b. Exportation avec la console MMC

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;i. Vous pouvez exporter le certificat racine de l’autorité de certification à partir de tout ordinateur joint au domaine à l’aide de la console MMC. Sélectionnez **Démarrer** et **Exécuter** ou ouvrez **Recherche** et tapez **MMC** pour l’ouvrir.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;II. Dans la console MMC, cliquez sur **Fichier**, puis sur **Ajouter/supprimer un composant logiciel enfichable**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;III. Dans la boîte de dialogue **Ajouter ou supprimer des composants logiciels enfichables**, sélectionnez **Certificats**, puis cliquez sur **Ajouter**. Dans l’invite, sélectionnez **Compte d’ordinateur**, puis sur **Suivant**. Dans la boîte de dialogue **Sélectionner un ordinateur**, sélectionnez **Ordinateur local**. Cliquez sur **Terminer**, puis sur **OK**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;IV. Développez **certificats (ordinateur Local)**. Développez **autorités de Certification racines de confiance**. Sélectionnez **certificats**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;v. Cliquez sur le certificat racine émis par votre autorité de certification. Cliquez avec le bouton droit sur le certificat, sélectionnez **Toutes les tâches** dans le menu, puis sélectionnez **Exporter**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;VI. L’**Assistant Exportation du certificat** s’affiche. Cliquez sur **Suivant**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;VII. Dans la boîte de dialogue **Format du fichier d’exportation**, sélectionnez le format de l’exportation. L’option recommandée est **Standard de syntaxe de message cryptographique - Certificats PKCS #7 (P7b)**. Si c’est ainsi que votre choix, n’oubliez pas de sélectionner également la case à cocher **inclure tous les certificats dans le chemin d’accès de certification si possible** , tel qu’il sera également exporter la chaîne de certificats, notamment le certificat d’autorité de certification racine et tous les certificats intermédiaires. Cliquez sur **Suivant**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;VIII. Dans la boîte de dialogue **Fichier à exporter**, dans l’entrée de nom de fichier, tapez un nom et un chemin d’accès de fichier (l’extension par défaut est .p7b) pour le certificat exporté. S’il est plus facile de vous, cliquez sur le bouton **Parcourir** pour accéder à l’emplacement que vous souhaitez enregistrer le certificat exporté à et nommez le certificat exporté ici. Cliquez sur **Enregistrer**, puis cliquez sur **suivant** lorsque vous êtes prêt.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;IX. Consultez le résumé de vos actions et cliquez sur **Terminer** pour achever l’exportation du certificat. Cliquez sur **OK** pour confirmer l’exportation.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;x. Copiez le fichier .p7b sur chacun de vos serveurs Edge.
    
### <a name="2-import-the-ca-certification-chain"></a>2. importer la chaîne de certification d’autorité de certification

&nbsp;&nbsp;&nbsp;un. Sur chaque serveur Edge, ouvrez la console MMC (cliquez sur **Démarrer** et **exécuter**ou **recherche**et tapez **MMC** pour ouvrir).
    
&nbsp;&nbsp;&nbsp;b. Dans le menu **Fichier**, cliquez sur **Ajouter/Supprimer un composant logiciel enfichable**, puis sur **Ajouter**.
    
&nbsp;&nbsp;&nbsp;c. Dans la boîte de dialogue **Ajouter ou supprimer des composants logiciels enfichables**, cliquez sur **Certificats**, puis sur **Ajouter**.
    
&nbsp;&nbsp;&nbsp;d. Dans la boîte de dialogue **Composant logiciel enfichable Certificats**, cliquez sur **Compte d’ordinateur**, puis sur **Suivant**.
    
&nbsp;&nbsp;&nbsp;e. Dans la boîte de dialogue **Sélectionner un ordinateur**, assurez-vous que la case à cocher **Ordinateur local : (l’ordinateur sur lequel cette console s’exécute)** est activée, puis cliquez sur **Terminer**.
    
&nbsp;&nbsp;&nbsp;f. Cliquez sur **Fermer**, puis sur **OK**.
    
&nbsp;&nbsp;&nbsp;g. Dans l’arborescence de la console, développez **Certificats (ordinateur local)**, cliquez avec le bouton droit sur **Autorités de certification racines de confiance**, sélectionnez **Toutes les tâches**, puis cliquez sur **Importer**.
    
&nbsp;&nbsp;&nbsp;h. Dans l’Assistant qui s’affiche, dans la zone **Fichier à importer**, spécifiez le nom de fichier du certificat (nom attribué au fichier .p7b dans la section précédente). Cliquez sur **Suivant**.
    
&nbsp;&nbsp;&nbsp;i. Laissez la case d’option **Placer tous les certificats dans le magasin suivant comme autorités de certification racines approuvées** activée. Cliquez sur **Suivant**.
    
&nbsp;&nbsp;&nbsp;j. Consultez le résumé, puis cliquez sur **Terminer** pour finaliser l’importation.
    
&nbsp;&nbsp;&nbsp;k. Cela vous devrez être effectuée pour chaque serveur Edge que vous déployez.
    
### <a name="3-create-the-certificate-request"></a>3. créer la demande de certificat

&nbsp;&nbsp;&nbsp;un. Ouvrez une session sur un de vos serveurs Edge, démarrez l’Assistant Déploiement et sous **étape 3 : demander, installer ou assigner les certificats**, cliquez sur **exécuter** (ou **Réexécuter**, si vous avez déjà exécuté cet Assistant).
    
&nbsp;&nbsp;&nbsp;b. Dans la page **Demande de certificat**, assurez-vous que l’option **Certificat Edge interne** est sélectionnée, puis cliquez sur **Demande**.
    
&nbsp;&nbsp;&nbsp;c. Dans la page **demandes différées ou immédiates** , sélectionnez **Envoyer la demande immédiatement à une autorité de certification en ligne** , si vous avez accès à un à partir de votre environnement serveur Edge ou **préparer la demande maintenant, mais l’envoyer plus tard** dans le cas contraire.
    
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
    
&nbsp;&nbsp;&nbsp;k. Dans la page **Résumé de la demande** , passez en revue les informations de certificat qui doit être utilisé pour générer votre demande. Si vous devez apporter des modifications, revenez en arrière pour le faire.
    
&nbsp;&nbsp;&nbsp;l. Cliquez sur **suivant** pour générer le fichier CSR que vous devrez fournir à l’autorité de certification (vous pouvez également cliquer sur **Afficher le journal** pour consulter le journal de la demande de certificat).
    
&nbsp;&nbsp;&nbsp;m. Une fois la demande générée, vous pouvez cliquer sur **Afficher** pour consulter le certificat et sur **Terminer** pour fermer la fenêtre. Le contenu du fichier CSR doit être affecté à votre autorité de certification afin qu’elle puisse générer un certificat que vous pourrez importer sur cet ordinateur dans la section suivante.
    

### <a name="4-import-the-certificate"></a>4. importer le certificat

&nbsp;&nbsp;&nbsp;un. Ouvrez une session, en tant que membre du groupe local Administrateurs sur le serveur Edge effectuées à partir de votre demande de certificat dans la dernière procédure.
    
&nbsp;&nbsp;&nbsp;b. Dans l’Assistant déploiement, en regard d’étape 3 de **. Demander, installer ou assigner les certificats**, cliquez sur **Réexécuter**.
    
&nbsp;&nbsp;&nbsp;c. Dans la page **Tâches se rapportant aux certificats disponibles**, cliquez sur **Importer un certificat à partir d’un fichier .P7b, .pfx ou .cer**.
    
&nbsp;&nbsp;&nbsp;d. Dans la page **Importer un certificat**, tapez le chemin complet et le nom du fichier du certificat que vous avez reçu dans la section précédent (ou cliquez sur **Parcourir** pour rechercher et sélectionner le fichier).
    
&nbsp;&nbsp;&nbsp;e. Si vous importez des certificats pour les autres membres de votre pool de serveurs Edge et que votre certificat contient une clé privée, veillez à sélectionner la case à cocher **fichier de certificat qui contient la clé privée du certificat** et spécifiez le mot de passe. Cliquez sur **Suivant** pour continuer.
    
&nbsp;&nbsp;&nbsp;f. Dans la page**Résumé** , cliquez sur **suivant** une fois que vous avez confirmé les informations et **Terminer** une fois le certificat importé avec succès.
    
 
### <a name="5-export-the-certificate"></a>5. exporter le certificat

&nbsp;&nbsp;&nbsp;un. Assurez-vous que vous avez ouvert une session sur le serveur de périphérie que vous avez importé le certificat à précédemment, en tant que membre du groupe Administrateurs local.
    
&nbsp;&nbsp;&nbsp;b. Cliquez sur **Démarrer**, sur **exécuter** (ou ouvrir **recherche** ), puis tapez **MMC**.
    
&nbsp;&nbsp;&nbsp;c. Dans la console MMC, cliquez sur **Fichier**, puis sur **Ajouter/Supprimer un composant logiciel enfichable**.
    
&nbsp;&nbsp;&nbsp;d. Dans la boîte de dialogue **Ajouter ou supprimer des composants logiciels enfichables**, cliquez sur **Certificats**, puis sur **Ajouter**.
    
&nbsp;&nbsp;&nbsp;e. Dans la boîte de dialogue composant logiciel enfichable **certificats** , sélectionnez le **compte d’ordinateur**. Cliquez sur **Suivant**.
    
&nbsp;&nbsp;&nbsp;f. Dans la boîte de dialogue **Sélectionner un ordinateur**, sélectionnez **Ordinateur local : (l’ordinateur sur lequel cette console s’exécute)**. Cliquez sur **Terminer**. La configuration de la console MMC est terminée.
    
&nbsp;&nbsp;&nbsp;g. Double-cliquez sur **Certificats (ordinateur local)** pour développer les magasins de certificats. Double-cliquez sur **personnel**, puis cliquez sur **certificats**.
    
  > [!NOTE]
  > Vous serez peut-être ici, et vous ne voyez pas tous les certificats dans le personnel de certificats stocker pour l’ordinateur local. Vous n’avez pas besoin de recherche, si la touche ne s pas, importé certificat n’ait une clé privée qui lui est associée. Essayez la demande importer les étapes ci-dessus une fois de plus et si vous êtes sûr que vous avez droit que, parler à votre administrateur de l’autorité de certification ou le fournisseur. 
  
&nbsp;&nbsp;&nbsp;h. Dans le **magasin personnel de certificats** de l’ordinateur local, cliquez sur le certificat que vous exportez. Sélectionnez **Toutes les tâches** dans le menu qui s’affiche, puis cliquez sur **Exporter**.
    
&nbsp;&nbsp;&nbsp;i. Dans l’**Assistant Exportation du certificat**, cliquez sur **Suivant**. Sélectionnez **Oui, exporter la clé privée**. Cliquez sur **Suivant**.
    
&nbsp;&nbsp;&nbsp;j. Dans la boîte de dialogue **Exporter les formats de fichiers**, sélectionnez **Échange d’informations personnelles – PKCS#12 (.PFX)**, puis les éléments suivants :
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;i. Incluez tous les certificats dans le chemin d’accès de certification, si possible.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;II. Exportez toutes les propriétés étendues.
    
   > [!NOTE]
   > Ne sélectionnez **JAMAIS****Supprimer la clé privée si l’exportation s’est terminée correctement**. Cela vous signifie que vous devez réimporter le certificat et la clé privée sur ce serveur Edge.
  
&nbsp;&nbsp;&nbsp;k. Si vous souhaitez affecter un mot de passe pour protéger la clé privée, vous pouvez taper un mot de passe pour cette clé. Entrez de nouveau le mot de passe pour le confirmer, puis cliquez sur **Suivant**.
    
&nbsp;&nbsp;&nbsp;l. Tapez un chemin d’accès et un nom de fichier avec l’extension **.pfx** pour le certificat exporté. Le chemin d’accès soit doit être accessible par d’autres serveurs de périphérie dans le pool, ou vous devez déplacer le fichier au moyen d’un support externe (par exemple, une clé USB). Lorsque vous avez effectué votre choix, cliquez sur **suivant** .
    
&nbsp;&nbsp;&nbsp;m. Consultez le résumé dans la boîte de dialogue **Fin de l’Assistant Exportation du certificat**, puis cliquez sur **Terminer**.
    
&nbsp;&nbsp;&nbsp;n. Cliquez sur **OK** dans la boîte de dialogue indiquant que l’exportation a abouti.
    
 
### <a name="6-assign-the-certificate"></a>6. assigner le certificat

&nbsp;&nbsp;&nbsp;un. Sur chaque serveur de périphérie, dans l’Assistant déploiement, en regard d’étape 3 de **. Demander, installer ou assigner les certificats**, cliquez sur **exécuter**.
    
&nbsp;&nbsp;&nbsp;b. Dans la page **Tâches se rapportant aux certificats disponibles**, cliquez sur **Affecter un certificat existant**.
    
&nbsp;&nbsp;&nbsp;c. Dans la page **Affectation de certificat**, sélectionnez **Serveur Edge interne** dans la liste.
    
&nbsp;&nbsp;&nbsp;d. Dans la page **Magasin de certificats** , sélectionnez le certificat que vous avez importés pour la bordure interne (à partir de la section précédente).
    
&nbsp;&nbsp;&nbsp;e. Dans la page **Résumé de l’affectation du certificat**, vérifiez vos paramètres, puis cliquez sur **Suivant** pour affecter le certificat.
    
&nbsp;&nbsp;&nbsp;f. Dans la page de fin de l’Assistant, cliquez sur **Terminer**.
    
&nbsp;&nbsp;&nbsp;g. Une fois que vous avez terminé cette procédure, il est recommandé pour ouvrir le composant logiciel enfichable MMC certificats sur chaque serveur Edge, développez **certificats (ordinateur Local)**, développez **personnel**, cliquez sur **certificats**et vérifiez que le serveur Edge interne certificat est répertorié dans le volet détails.
    
### <a name="external-edge-interface-certificates"></a>Certificats d’interface externe de serveur Edge

 
### <a name="1-create-the-certificate-request"></a>1. créer la demande de certificat

&nbsp;&nbsp;&nbsp;un. Ouvrez une session sur un de vos serveurs Edge, démarrez l’Assistant Déploiement et sous **étape 3 : demander, installer ou assigner les certificats, cliquez sur Exécuter** (ou **Réexécuter**, si vous avez déjà exécuté cet Assistant).
    
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
    
&nbsp;&nbsp;&nbsp;k. Dans la page **Paramètre du domaine SIP sur les autres noms du sujet (SAN)** , cochez la case à cocher du domaine pour ajouter un sip.<sipdomain> entrée à la liste des autres noms du sujet.
    
&nbsp;&nbsp;&nbsp;l. Dans la page **Configurer d’autres noms du sujet supplémentaires**, ajoutez les autres noms du sujet supplémentaires nécessaires.
    
&nbsp;&nbsp;&nbsp;m. Dans la page **Résumé de la demande** , passez en revue les informations de certificat qui doit être utilisé pour générer votre demande. Si vous devez apporter des modifications, revenez en arrière pour le faire.
    
&nbsp;&nbsp;&nbsp;n. Lorsque vous êtes prêt, cliquez sur **suivant** pour générer le fichier CSR que vous devrez fournir à l’autorité de certification (vous pouvez également cliquer sur **Afficher le journal** pour consulter le journal de la demande de certificat).
    
&nbsp;&nbsp;&nbsp;o. Une fois la demande générée, vous pouvez cliquer sur **Afficher** pour consulter le certificat et sur **Terminer** pour fermer la fenêtre. Le contenu du fichier CSR doit être affecté à votre autorité de certification afin qu’elle puisse générer un certificat que vous pourrez importer sur cet ordinateur dans la section suivante.
    
&nbsp;&nbsp;&nbsp;p. (FACULTATIF) Il est possible que vous soyez invité à fournir certaines informations lors de l’envoi de la demande de signature de certificat (CSR), comme suit (les autorités de certification varient considérablement, de sorte que ce n’est peut-être pas obligatoire) :
    
  - **Microsoft** comme plateforme serveur
    
  - **Services Internet (IIS)** comme version
    
  - **Serveur web** comme type d’utilisation
    
  - **PKCS7** comme réponse
    
 
### <a name="2-import-the-certificate"></a>2. importer le certificat

&nbsp;&nbsp;&nbsp;un. Ouvrez une session, en tant que membre du groupe local Administrateurs sur le serveur Edge effectuées à partir de votre demande de certificat dans la dernière procédure.
    
&nbsp;&nbsp;&nbsp;b. Dans l’Assistant déploiement, en regard d’étape 3 de **. Demander, installer ou assigner les certificats**, cliquez sur **Réexécuter**.
    
&nbsp;&nbsp;&nbsp;c. Dans la page **Tâches se rapportant aux certificats disponibles**, cliquez sur **Importer un certificat à partir d’un fichier .P7b, .pfx ou .cer**.
    
&nbsp;&nbsp;&nbsp;d. Dans la page **Importer un certificat**, tapez le chemin complet et le nom du fichier du certificat que vous avez reçu dans la section précédent (ou cliquez sur **Parcourir** pour rechercher et sélectionner le fichier). Si votre certificat contient une clé privée, veillez à sélectionner le **fichier de certificat contient la clé privée du certificat**et entrez le mot de passe de la clé privée. Cliquez sur **Suivant** pour continuer.
    
&nbsp;&nbsp;&nbsp;e. Dans la page **Importer le résumé du certificat**, vérifiez les informations résumées, puis cliquez sur **Suivant**.
    
&nbsp;&nbsp;&nbsp;f. Dans la page **Exécution de commandes** , vous pouvez consulter le résultat de l’importation lorsqu’elle est complète en cliquant sur **Afficher le journal**. Cliquez sur **Terminer** pour terminer l’importation du certificat.
    
&nbsp;&nbsp;&nbsp;g. Si vous avez d’autres serveurs de périphérie dans un pool, vous devez suivre les deux procédures suivantes ainsi. S’il s’agit d’un serveur Edge autonome, vous avez terminé avec les certificats externes.
    
 
### <a name="3-export-the-certificate"></a>3. exporter le certificat

&nbsp;&nbsp;&nbsp;un. Assurez-vous que vous avez ouvert une session sur le serveur de périphérie que vous avez importé le certificat en tant qu’administrateur local.
    
&nbsp;&nbsp;&nbsp;b. Cliquez sur **Démarrer**, sur **exécuter** (ou ouvrir **recherche** ), puis tapez **MMC**.
    
&nbsp;&nbsp;&nbsp;c. Dans la console MMC, cliquez sur **Fichier**, puis sur **Ajouter/Supprimer un composant logiciel enfichable**.
    
&nbsp;&nbsp;&nbsp;d. Dans la boîte de dialogue **Ajouter ou supprimer des composants logiciels enfichables**, cliquez sur **Certificats**, puis sur **Ajouter**.
    
&nbsp;&nbsp;&nbsp;e. Dans la boîte de dialogue composant logiciel enfichable **certificats** , sélectionnez le **compte d’ordinateur**. Cliquez sur **Suivant**.
    
&nbsp;&nbsp;&nbsp;f. Dans la boîte de dialogue **Sélectionner un ordinateur**, sélectionnez **Ordinateur local : (l’ordinateur sur lequel cette console s’exécute)**. Cliquez sur **Terminer**. La configuration de la console MMC est terminée.
    
&nbsp;&nbsp;&nbsp;g. Double-cliquez sur **Certificats (ordinateur local)** pour développer les magasins de certificats. Double-cliquez sur **Personnel**, puis sur **Certificats**.
    
   > [!NOTE]
   > Vous serez peut-être ici, et vous ne voyez pas tous les certificats dans le personnel de certificats stocker pour l’ordinateur local. Vous n’avez pas besoin de recherche, si la touche ne s pas, importé certificat n’ait une clé privée qui lui est associée. Essayez la demande importer les étapes ci-dessus une fois de plus et si vous êtes sûr que vous avez droit que, parler à votre administrateur de l’autorité de certification ou le fournisseur. 
  
&nbsp;&nbsp;&nbsp;h. Dans le **magasin personnel de certificats** de l’ordinateur local, cliquez sur le certificat que vous exportez. Sélectionnez **Toutes les tâches** dans le menu qui s’affiche, puis cliquez sur **Exporter**.
    
&nbsp;&nbsp;&nbsp;i. Dans l’**Assistant Exportation du certificat**, cliquez sur **Suivant**. Sélectionnez **Oui, exporter la clé privée**. Cliquez sur **Suivant**.
    
   > [!NOTE]
   > Si **Oui, exporter la clé privée** n’est pas disponible, la clé privée de ce certificat n’a pas été marquée pour l’exportation avant que vous l’avez compris. Pour pouvoir poursuivre l’exportation, vous devez faire une nouvelle demande de certificat auprès du fournisseur en vous assurant que le certificat est marqué pour l’exportation.
  
&nbsp;&nbsp;&nbsp;j. Dans la boîte de dialogue Exporter les formats de fichiers, sélectionnez Échange d’informations personnelles – PKCS#12 (.PFX), puis les éléments suivants :
    
 &nbsp;&nbsp;&nbsp;i. Incluez tous les certificats dans le chemin d’accès de certification, si possible.
    
 &nbsp;&nbsp;&nbsp;II. Exportez toutes les propriétés étendues.
    
   > [!NOTE]
   > Ne sélectionnez **JAMAIS****Supprimer la clé privée si l’exportation s’est terminée correctement**. Cela vous signifie que vous devez réimporter le certificat et la clé privée sur ce serveur Edge.
  
&nbsp;&nbsp;&nbsp;k. Si vous souhaitez affecter un mot de passe pour protéger la clé privée, vous pouvez taper un mot de passe pour cette clé. Entrez de nouveau le mot de passe pour le confirmer, puis cliquez sur **Suivant**.
    
&nbsp;&nbsp;&nbsp;l. Tapez un chemin d’accès et un nom de fichier avec l’extension **.pfx** pour le certificat exporté. Le chemin d’accès soit doit être accessible par d’autres serveurs de périphérie dans le pool, ou vous devez déplacer le fichier au moyen d’un support externe (par exemple, une clé USB). Lorsque vous avez effectué votre choix, cliquez sur **suivant** .
    
&nbsp;&nbsp;&nbsp;m. Consultez le résumé dans la boîte de dialogue **Fin de l’Assistant Exportation du certificat**, puis cliquez sur **Terminer**.
    
&nbsp;&nbsp;&nbsp;n. Cliquez sur **OK** dans la boîte de dialogue indiquant que l’exportation a abouti.
    
&nbsp;&nbsp;&nbsp;o. Vous devez maintenant revenir l’importation de la section avant ce certificat et importer le certificat sur tous vos serveurs Edge restants, puis poursuivre l’affectation, vous trouverez ci-dessous.
    
 
### <a name="4-assign-the-certificate"></a>4. assigner le certificat

&nbsp;&nbsp;&nbsp;un. Sur **chaque** serveur de périphérie, dans l’Assistant déploiement, en regard d’étape 3 de **. Demander, installer ou assigner les certificats**, cliquez sur **exécuter**.
    
&nbsp;&nbsp;&nbsp;b. Dans la page **Tâches se rapportant aux certificats disponibles**, cliquez sur **Affecter un certificat existant**.
    
&nbsp;&nbsp;&nbsp;c. Dans la page **Assignation de certificat** , sélectionnez **Serveur Edge externe** dans la liste.
    
&nbsp;&nbsp;&nbsp;d. Dans la page **Magasin de certificats** , sélectionnez le certificat que vous avez importé pour le périmètre externe (à partir de la section précédente).
    
&nbsp;&nbsp;&nbsp;e. Dans la page **Résumé de l’affectation du certificat**, vérifiez vos paramètres, puis cliquez sur **Suivant** pour affecter le certificat.
    
&nbsp;&nbsp;&nbsp;f. Dans la page de fin de l’Assistant, cliquez sur **Terminer**.
    
&nbsp;&nbsp;&nbsp;g. Une fois que vous avez terminé cette procédure, il est recommandé pour ouvrir le composant logiciel enfichable MMC certificats sur chaque serveur, développez **certificats (ordinateur Local)**, développez **personnel**, cliquez sur **certificats**et vérifiez que le serveur Edge interne certificat est répertorié dans le volet détails.
    
   > [!NOTE]
   > Vous devez également configurer les certificats pour votre serveur de proxy inverse. 
  
## <a name="starting-the-edge-servers"></a>Démarrer les serveurs de périphérie

Une fois l’installation terminée, vous devez démarrer les services sur chaque serveur de périphérie dans votre déploiement :
  
1. Sur chaque serveur Edge, dans l' **Assistant Déploiement**, à côté **étape 4 : démarrer les Services**, cliquez sur **exécuter**.
    
2. Dans la page **Démarrer la Skype pour les Services de serveur** , passez en revue la liste des services, puis cliquez sur **suivant** pour démarrer les services.
    
3. Une fois les services lancés, cliquez sur **Terminer** pour fermer l’Assistant.
    
4. (Facultatif) Toujours sous l’**Étape 4 : Lancement des services**, cliquez sur **État des services**.
    
5.  Dans la console **MMC Services** sur chaque serveur, vérifiez que tous les Skype pour les services Business Server sont en cours d’exécution.
    

