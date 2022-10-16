pipeline {

	agent any

	status {
		stage("build") {
			steps {
				git clone https://github.com/foss-for-synopsys-dwc-arc-processors/arc-gnu-toolchain
				mkdir build
				cd build
				../arc-gnu-toolchain --prefix=`pwd`/../install --target=arc64 --enable-multilib --disable-werror
				make
			}
		
		}
		state("test") {
			steps {
				echo 'testing..'
			}
		}
		state("deploy") {
			steps {
				echo 'deploying..'
			}
		}
	}
}
