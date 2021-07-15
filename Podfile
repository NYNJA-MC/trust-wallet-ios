platform :ios, '12.0'
inhibit_all_warnings!
source 'https://github.com/CocoaPods/Specs.git'

target 'Trust' do
  use_frameworks!

  pod 'BigInt', '~> 5.0'
  pod 'R.swift'
  pod 'JSONRPCKit', '~>3.0'
  pod 'PromiseKit', '~> 6.0'
  pod 'APIKit'
  pod 'Eureka', '~>5.3'
  pod 'MBProgressHUD'
  pod 'StatefulViewController'
  pod 'QRCodeReaderViewController', :git=>'https://github.com/yannickl/QRCodeReaderViewController.git', :branch=>'master'
  pod 'KeychainSwift'
  pod 'SwiftLint'
  pod 'SeedStackViewController', '~>0.5'
  pod 'RealmSwift', '~>10.5.1'
  pod 'Moya', '~> 14'
  pod 'CryptoSwift', '~>1.4'
  pod 'Kingfisher', '~> 6.0'
  pod 'TrustCore', :git=>'https://github.com/TrustWallet/trust-core', :branch=>'master'
  pod 'TrustKeystore', :git=>'https://github.com/TrustWallet/trust-keystore', :branch=>'master'
  pod 'TrezorCrypto'
  pod 'Branch'
  pod 'SAMKeychain'
  pod 'TrustWeb3Provider', :git=>'https://github.com/TrustWallet/trust-web3-provider', :commit=>'f4e0ebb1b8fa4812637babe85ef975d116543dfd'
  pod 'URLNavigator'
  pod 'TrustWalletSDK', :git=>'https://github.com/TrustWallet/TrustSDK-iOS', :branch=>'master'

  # add the Firebase pod for Google Analytics
  pod 'Firebase/Analytics'
  # or pod ‘Firebase/AnalyticsWithoutAdIdSupport’
  # for Analytics without IDFA collection capability

  # add pods for any other desired Firebase products
  # https://firebase.google.com/docs/ios/setup#available-pods
  
  target 'TrustTests' do
    inherit! :search_paths
    # Pods for testing
  end

  target 'TrustUITests' do
    inherit! :search_paths
    # Pods for testing
  end

end

post_install do |installer|
  installer.pods_project.targets.each do |target|
    if ['JSONRPCKit'].include? target.name
      target.build_configurations.each do |config|
        config.build_settings['SWIFT_VERSION'] = '4.0'
      end
    end
    if ['TrustKeystore'].include? target.name
      target.build_configurations.each do |config|
        config.build_settings['SWIFT_OPTIMIZATION_LEVEL'] = '-Owholemodule'
      end
    end
    # if target.name != 'Realm'
    #     target.build_configurations.each do |config|
    #         config.build_settings['MACH_O_TYPE'] = 'staticlib'
    #     end
    # end
  end
end
