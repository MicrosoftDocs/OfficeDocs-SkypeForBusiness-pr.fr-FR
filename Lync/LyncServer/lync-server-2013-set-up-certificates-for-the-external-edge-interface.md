---
title: 'Lync Server 2013 : configuration des certificats pour l’interface Edge externe'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up certificates for the external edge interface
ms:assetid: 5d78182c-88d8-4483-95ad-74b17f2d5fac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398409(v=OCS.15)
ms:contentKeyID: 48184287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0aadbc9603fb62a2dacf78129aef3bf448da2f05
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143404"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="set-up-certificates-for-the-external-edge-interface-for-lync-server-2013"></a>Configurer des certificats pour l’interface Edge externe pour Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-08_

<div>


> [!IMPORTANT]  
> Lorsque vous exécutez l’Assistant Certificat, veillez à être connecté avec un compte membre d’un groupe auquel les autorisations appropriées ont été octroyées pour le type de modèle de certificat que vous allez utiliser. Par défaut, une demande de certificat Lync Server utilise le modèle de certificat de serveur Web. Si vous utilisez un compte membre du groupe RTCUniversalServerAdmins pour demander un certificat qui utilise ce modèle, vérifiez que le groupe possède les autorisations d’inscription requises pour utiliser ce modèle.



</div>

Chaque serveur Edge nécessite un certificat public sur l’interface entre le réseau de périmètre et Internet, et l’autre nom de sujet du certificat doit contenir les noms externes du service Edge d’accès et du service Edge de conférence Web. noms de domaine qualifiés (FQDN).

Pour plus d’informations à ce sujet et sur d’autres exigences de certificat, voir [Certificate Requirements for External User Access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).

Pour obtenir la liste des autorités de certification publiques qui fournissent des certificats conformes aux exigences spécifiques pour les certificats de communications unifiées et qui ont conclu un partenariat avec Microsoft afin de s’assurer qu’ils fonctionnent avec l’Assistant Certificat Lync Server 2013, consultez l’article 929395 de la base de connaissances Microsoft « partenaires de certificat de communications [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834)unifiées pour Exchange Server et Communications Server » à l’adresse.

<div>

## <a name="configuring-certificates-on-the-external-interfaces"></a>Configuration des certificats sur les interfaces externes

Pour configurer un certificat sur l’interface Edge externe sur un site, utilisez les procédures de cette section pour effectuer les opérations suivantes :

  - Créez la demande de certificat pour l’interface externe du serveur Edge.

  - Envoyez la demande à votre autorité de certification publique.

  - Importez le certificat pour l’interface externe de chaque serveur Edge.

  - Affectez le certificat pour l’interface externe de chaque serveur Edge.

  - Si votre déploiement comprend plusieurs serveurs Edge, exportez le certificat avec sa clé privée, puis copiez-le sur les autres serveurs Edge. Ensuite, pour chaque serveur Edge, importez-le et affectez-le comme décrit précédemment. Répétez cette procédure pour chaque serveur Edge.

Vous pouvez demander des certificats publics directement auprès d’une autorité de certification publique (par exemple, à partir du site Web d’une autorité de certification publique). Les procédures de cette section utilisent l’Assistant Certificat pour la plupart des tâches de certificat. Si vous avez choisi de demander un certificat directement auprès d’une autorité de certification publique, vous devrez modifier chaque procédure comme il convient pour demander, transporter et importer le certificat, ainsi que pour importer la chaîne de certificats.

Lorsque vous demandez un certificat à une autorité de certification externe, les informations d’identification fournies doivent disposer des autorisations nécessaires pour demander un certificat à cette autorité de certification. Chaque autorité de certification dispose d’une stratégie de sécurité qui définit les informations d’identification (c’est-à-dire, les noms d’utilisateur et de groupe spécifiques) qui sont autorisées à demander, à émettre, à gérer ou à lire des certificats.

Si vous décidez d’utiliser la console MMC (Microsoft Management Console) certificats pour importer la chaîne de certificats et le certificat, vous devez les importer dans le magasin de certificats de l’ordinateur. Si vous les importez dans le magasin de certificats d’utilisateur ou de service, le certificat ne sera pas disponible pour affectation dans l’Assistant Certificat Lync Server 2013.

<div>

## <a name="to-create-the-certificate-request-for-the-external-interface-of-the-edge-server"></a>Pour créer la demande de certificat pour l’interface externe du serveur Edge

1.  Sur le serveur Edge, dans l’Assistant Déploiement, à côté d’**Étape 3 : Demander, installer ou assigner les certificats**, cliquez sur **Réexécuter**.
    
    <div>
    

    > [!NOTE]  
    > Si votre organisation souhaite prendre en charge la connectivité PIC avec AOL, vous ne pouvez pas utiliser l’Assistant Déploiement de Lync Server pour demander le certificat. Au lieu de cela, effectuez les étapes de la procédure « pour créer une demande de certificat pour l’interface externe du serveur Edge pour la prise en charge de la connectivité PIC avec AOL », plus loin dans cette rubrique.<BR>Si vous disposez de plusieurs serveurs Edge dans un même emplacement d’un pool, vous pouvez exécuter l’Assistant Certificat Lync Server 2013 sur l’un des serveurs Edge.

    
    </div>

2.  Dans la page **Tâches se rapportant aux certificats disponibles**, cliquez sur **Créer une demande de certificat**.

3.  Dans la page **Demande de certificat**, cliquez sur **Certificat de serveur Edge externe**.

4.  Dans la page **Demande différée ou immédiate**, cochez la case **Préparer la demande maintenant, mais l’envoyer plus tard**.

5.  Dans la **page fichier de demande de certificat** , tapez le chemin d’accès complet et le nom du fichier dans lequel la demande doit être enregistrée (par exemple,\\c\_:\_CERT exernal Edge. cer).

6.  Dans la page **Spécifier un autre modèle de certificat**, pour utiliser un autre modèle que le modèle WebServer par défaut, cochez la case **Utiliser un autre modèle de certificat pour l’autorité de certification sélectionnée**.

7.  Dans la page **Nom et paramètres de sécurité**, procédez comme suit :
    
      - Dans **Nom convivial**, tapez un nom d’affichage du certificat.
    
      - Dans **longueur en bits**, spécifiez la longueur en bits (généralement, la valeur par défaut de **2048**).
    
      - Vérifiez que la case **Marquer la clé privée du certificat comme exportable** est cochée.

8.  Dans la page **Informations relatives à l’organisation**, tapez le nom de l’organisation et de l’unité d’organisation (par exemple, une division ou un service).

9.  Dans la page **Informations géographiques**, spécifiez les informations d’emplacement.

10. Dans la page **Nom du sujet/Autres noms du sujet**, le système affiche les informations automatiquement renseignées par l’Assistant. Si d’autres noms du sujet doivent être ajoutés, spécifiez-les dans les deux étapes suivantes.

11. Sur la page **paramètre du domaine SIP sur les autres noms du sujet** , activez la case à cocher domaine pour ajouter un SIP. \<entrée\> sipdomain à la liste des autres noms du sujet.

12. Dans la page **Configurer d’autres noms du sujet supplémentaires** , spécifiez les autres noms du sujet supplémentaires nécessaires.

13. Dans la page **Résumé de la demande**, vérifiez les informations de certificat à utiliser pour générer la demande.

14. Une fois l’exécution des commandes terminée, procédez comme suit :
    
      - Pour afficher le journal de la demande de certificat, cliquez sur **afficher le journal**.
    
      - Pour terminer la demande de certificat, cliquez sur **suivant**.

15. Dans la page **fichier de demande de certificat** , procédez comme suit :
    
      - Pour afficher le fichier de demande de signature de certificat (CSR) généré, cliquez sur **Afficher**.
    
      - Pour fermer l’Assistant, cliquez sur **Terminer**.

16. Copiez le fichier de sortie dans un emplacement où vous pouvez l’envoyer à l’autorité de certification publique.

</div>

<div>

## <a name="to-create-a-certificate-request-for-the-external-interface-of-the-edge-server-to-support-public-im-connectivity-with-aol"></a>Pour créer une demande de certificat pour l’interface externe du serveur Edge, afin de prendre en charge la connectivité PIC avec AOL

1.  Lorsque le modèle requis est disponible pour l’autorité de certification, utilisez la cmdlet Windows PowerShell suivante à partir du serveur Edge pour demander le certificat :
    
        Request-CsCertificate -New -Type AccessEdgeExternal  -Output C:\ <certfilename.txt or certfilename.csr>  -ClientEku $true -Template <template name>
    
    Le nom de certificat par défaut du modèle fourni dans Lync Server 2013 est le serveur Web. Ne spécifiez \<le nom\> du modèle que si vous devez utiliser un modèle différent du modèle par défaut.
    
    <div>
    

    > [!NOTE]  
    > Si votre organisation souhaite prendre en charge la connectivité PIC avec AOL, vous devez utiliser Windows PowerShell au lieu de l’Assistant Certificat pour demander que le certificat soit attribué au serveur Edge externe pour le service Edge d’accès. Cela est dû au fait que le modèle de serveur Web Lync Server 2013 que l’Assistant certificat utilise pour demander un certificat ne prend pas en charge la configuration EKU du client. Avant d’utiliser Windows PowerShell pour créer le certificat, l’administrateur de l’autorité de certification doit créer et déployer un nouveau modèle qui prend en charge l’utilisation améliorée de la variable client.

    
    </div>

</div>

<div>

## <a name="to-submit-a-request-to-a-public-certification-authority"></a>Pour envoyer une demande à une autorité de certification publique

1.  Ouvrez le fichier de sortie.

2.  Copiez et collez le contenu de la demande de signature de certificat (CSR).

3.  Si vous y êtes invité, spécifiez les éléments suivants :
    
      - **Microsoft** en tant que plateforme serveur.
    
      - **IIS** comme version.
    
      - **Serveur Web** en tant que type d’utilisation.
    
      - **PKCS7** en tant que format de réponse.

4.  Lorsque l’autorité de certification publique a vérifié vos informations, vous recevez un message électronique contenant le texte requis pour votre certificat.

5.  Copiez le texte du message électronique et enregistrez-le dans un fichier texte (. txt) sur votre ordinateur local.

</div>

<div>

## <a name="to-import-the-certificate-for-the-external-interface-of-the-edge-server"></a>Pour importer le certificat pour l’interface externe du serveur Edge

1.  Ouvrez une session en tant que membre du groupe Administrateurs sur le serveur Edge sur lequel vous avez créé la demande de certificat.

2.  Dans l’Assistant Déploiement, dans la page **déployer le serveur Edge** , en regard de **étape 3 : demander, installer ou assigner les certificats**, cliquez sur **réexécuter**.

3.  Sur la page **tâches de certificats disponibles** , cliquez sur **Importer un certificat à partir d’un fichier. p7b, pfx ou. cer**.

4.  Sur la page **Importer un certificat** , cliquez sur **Parcourir** pour rechercher et sélectionner le certificat que vous avez demandé pour l’interface externe du serveur Edge (ou, vous pouvez taper le chemin d’accès complet et le nom de fichier). Si le certificat contient une clé privée, sélectionnez le **fichier de certificat contient la clé privée du certificat** et tapez le mot de passe de la clé privée. Cliquez sur **Suivant**.

5.  Dans la page **importer le résumé du certificat** , passez en revue le résumé, puis cliquez sur **suivant**.

6.  Lors de l' **exécution de commandes**, passez en revue les résultats de l’importation, cliquez sur **afficher le journal** pour obtenir plus d’informations, puis cliquez sur **Terminer** pour terminer l’importation du certificat.

7.  Si vous configurez un pool de serveurs Edge, exportez le certificat avec sa clé privée comme indiqué dans la procédure « pour exporter le certificat avec la clé privée pour les serveurs Edge dans un pool » plus loin dans cette rubrique. Copiez le fichier de certificat exporté vers les autres serveurs Edge et importez-le dans le magasin de l’ordinateur sur chaque serveur Edge.

</div>

<div>

## <a name="to-export-the-certificate-with-the-private-key-for-edge-servers-in-a-pool"></a>Pour exporter le certificat avec la clé privée pour les serveurs Edge dans un pool

1.  Ouvrez une session en tant que membre du groupe Administrateurs sur le serveur Edge sur lequel vous avez importé le certificat.

2.  Cliquez sur **Démarrer**, sur **exécuter**, puis tapez **MMC**.

3.  Dans la console MMC (Microsoft Management Console), cliquez sur **fichier**, puis sur **Ajouter/supprimer un composant logiciel enfichable**.

4.  Dans **Ajouter ou supprimer des composants logiciels enfichables**, cliquez sur **certificats**, puis sur **Ajouter**.

5.  Dans la boîte de dialogue **certificats** , sélectionnez **compte d’ordinateur**, cliquez sur **suivant**, sélectionnez **ordinateur local : (l’ordinateur sur lequel cette console est exécutée)** dans **Sélectionner un ordinateur**, cliquez sur **Terminer** , puis sur **OK** pour terminer la configuration de la console MMC.

6.  Double-cliquez sur **certificats (ordinateur local)** pour développer les magasins de certificats, double-cliquez sur **personnel**, puis sur **certificats**.
    
    <div>
    

    > [!IMPORTANT]  
    > S’il n’y a aucun certificat dans le magasin personnel de certificats pour l’ordinateur local, il n’y a pas de clé privée associée au certificat importé. Passez en revue les étapes de demande et d’importation. Si le problème persiste, contactez l’administrateur de votre autorité de certification ou votre fournisseur.

    
    </div>

7.  Dans le **magasin personnel de certificats de l’ordinateur local**, cliquez avec le bouton droit sur le certificat que vous exportez, cliquez sur **toutes les tâches**, puis sur **Exporter**.

8.  Dans l’Assistant exportation de certificat, cliquez sur **suivant**, sélectionnez **Oui, exporter la clé privée**, puis cliquez sur **suivant**.
    
    <div>
    

    > [!NOTE]  
    > Si la sélection est <STRONG>Oui, l’exportation de la clé privée</STRONG> n’est pas disponible, la clé privée associée à ce certificat n’a pas été marquée pour l’exportation. Vous devrez demander de nouveau le certificat, en vous assurant que le certificat est marqué pour autoriser l’exportation de la clé privée avant de pouvoir poursuivre l’exportation. Contactez l’administrateur ou le fournisseur de votre autorité de certification.

    
    </div>

9.  Dans la boîte de dialogue Exporter les formats de fichiers, sélectionnez **échange\#d’informations personnelles – PKCS 12 (. PFX)** , puis sélectionnez ce qui suit :
    
      - Inclure tous les certificats dans le chemin d’accès de certification si possible
    
      - Exporter toutes les propriétés étendues
        
        <div>
        

        > [!WARNING]  
        > Lorsque vous exportez le certificat à partir d’un serveur Edge, ne sélectionnez pas <STRONG>Supprimer la clé privée si l’exportation réussit</STRONG>. Si vous sélectionnez cette option, vous devez importer le certificat et la clé privée sur ce serveur Edge.

        
        </div>

10. Cliquez sur **Suivant**.

11. Tapez un mot de passe pour la clé privée, entrez de nouveau le mot de passe pour le confirmer, puis cliquez sur **suivant**.

12. Tapez un chemin d’accès et un nom de fichier pour le certificat exporté, à l’aide d’une extension de fichier. pfx. Le chemin d’accès doit être accessible à tous les autres serveurs Edge du pool ou être disponible pour le transport via un support amovible (par exemple, un lecteur flash USB). Cliquez sur **Suivant**.

13. Consultez le résumé dans **fin de l’Assistant Exportation du certificat**, puis cliquez sur **Terminer**.

14. Dans la boîte de dialogue exportation réussie, cliquez sur **OK**.

15. Importez le fichier de certificat exporté vers les autres serveurs Edge en suivant les étapes décrites dans la procédure « pour importer le certificat pour l’interface externe du serveur Edge » plus haut dans cette rubrique.

</div>

<div>

## <a name="to-assign-the-certificate-for-the-external-interface-of-the-edge-server"></a>Pour attribuer le certificat pour l’interface externe du serveur Edge

1.  Sur chaque serveur Edge, dans l’Assistant Déploiement, à côté de **étape 3 : demander, installer ou assigner les certificats**, cliquez sur **réexécuter**.

2.  Dans la page **tâches de certificats disponibles** , cliquez sur **affecter un certificat existant**.

3.  Dans la page **affectation de certificat** , cliquez sur certificat de serveur **Edge externe** et activez la case à cocher **utilisations de certificat avancées** .

4.  Sur la page **utilisations de certificat avancées** , activez toutes les cases à cocher pour attribuer le certificat à toutes les utilisations.

5.  Sur la page **magasin de certificats** , sélectionnez le certificat public que vous avez demandé et importé pour l’interface externe du serveur Edge.
    
    <div>
    

    > [!NOTE]  
    > Si le certificat que vous avez demandé et importé ne se trouve pas dans la liste, l’une des méthodes de dépannage consiste à vérifier que le nom de sujet et les autres noms de sujet du certificat répondent à toutes les exigences du certificat et, si vous avez importé manuellement le certificat et chaîne de certificats au lieu d’utiliser les procédures précédentes, le certificat se trouve dans le magasin de certificats correct (le magasin de certificats de l’ordinateur, pas le magasin de certificats de l’utilisateur ou du service).

    
    </div>

6.  Sur la page Résumé de l' **affectation du certificat** , vérifiez vos paramètres, puis cliquez sur **suivant** pour affecter les certificats.

7.  Dans la page de fin de l’Assistant, cliquez sur **Terminer**.

8.  Après avoir utilisé cette procédure pour attribuer le certificat de périphérie, ouvrez le composant logiciel enfichable certificat sur chaque serveur, développez **certificats (ordinateur local)**, développez **personnel**, cliquez sur **certificats**, puis vérifiez dans le volet d’informations que le certificat est affiché.

9.  Si votre déploiement comprend plusieurs serveurs Edge, répétez cette procédure pour chaque serveur Edge.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

